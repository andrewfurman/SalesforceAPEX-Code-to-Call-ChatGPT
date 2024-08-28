In certain scenarios, we need to make the webservice callout from the apex trigger to call an external webservice. We cannot call external web services synchronously from triggers, because calling a web service synchronously from triggers will hold up the database transaction until the callout completed. This will impact performance for other transactions. In this scenario we can invoke callouts from triggers by encapsulating the callouts in @future methods. Here is an example, how to invoke webservice callouts from trigger.

## Apex Class: Example

public class LeadTriggerHandler {

    @future (callout=true)
    public static void sendLeadInfo(string firstName, string lastName, string email) {
        try{
            HttpRequest request = new HttpRequest();
            HttpResponse response = new HttpResponse();
            Http http = new Http();

            request.setEndpoint('Your Endpoint URL');
            request.setHeader('Content-Type','application/json'); 
            request.setMethod('POST');
            request.setBody('fname='+EncodingUtil.urlEncode(firstName, 'UTF-8')+'&lname='+EncodingUtil.urlEncode(lastName, 'UTF-8')
                            '&email='+EncodingUtil.urlEncode(email, 'UTF-8'));
            request.setCompressed(true);

            response = http.send(request);
            if (response.getStatusCode() == 200) {
                System.debug('Response-' + response);
            }
        }
        catch(System.CalloutException e){
            System.debug('Error-' + e.getMessage());   
        }
    }
}


## Apex Trigger example:

trigger LeadTrigger on Lead (after insert) {

    for (Lead objLead : Trigger.new) {
        //make webservice callout 
        LeadTriggerHandler.sendLeadInfo(objLead.FirstName, objLead.LastName, objLead.Email);
    }
}