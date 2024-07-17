@testvisible
    private static RestTest createRestContext(String personEmail, String reqBody, String resBody, String param, Integer statusCode) {
        RestTest restTest = new RestTest();
        RestRequest req = new RestRequest();
        RestResponse res = new RestResponse();
        req.requestURI = REQUEST_URI_PERSACCOUNTS;
        req.httpMethod = GC_WS_PersonAccount_V2.LOG_API_TYPE_PUT;
   
        if(reqBody != null) {
            req.requestBody = Blob.valueOf(reqBody);
        } else {
            req.requestBody = Blob.valueOf('[{\"Email\":' +personEmail+ '}]');
        }

        RestContext.request = req;

        if (resBody != null) {
            res.responseBody = Blob.valueOf(resBody);
            RestContext.response = res;
        }
        
        if(param != null) {
            RestContext.request.addParameter('recovery', param);
        }

        if(statusCode != null) {
            res.statusCode = statusCode;
        }

        restTest.req = req;
        restTest.res = res;
        return restTest;
    }

    @testVisible
    private class RestTest {
        public RestRequest req;
        public RestResponse res;
    }

    RestTest restTest = createRestContext(TEST_UPSERT_ERROR, null, '{"status" : "Success"}', null, null);
        RestRequest req = restTest.req;
        RestResponse res = restTest.res;
