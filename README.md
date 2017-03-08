# GCMClientManager
Easy way to get token id from GCM in android

public String registation_id;
String PROJECT_NUMBER = "Enter Your Project ID Here";



@Override
    protected void onCreate(@Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
         GCMgetToken();
}



public void GCMgetToken() {
        GCMClientManager pushClientManager = new GCMClientManager(ChangeDevice.this, PROJECT_NUMBER);
        pushClientManager.registerIfNeeded(new GCMClientManager.RegistrationCompletedHandler() {
            @Override
            public void onSuccess(String registrationId, boolean isNewRegistration) {
                //Get Your Token id here
                registation_id = registrationId;
            }

            @Override
            public void onFailure(String ex) {
                super.onFailure(ex);
            }

        });
    }
