To install the namespace configuration operator https://github.com/redhat-cop/namespace-configuration-operator

Apply the following manifests:

# Create namespace
oc apply -f namespace.yaml

# Create subscription / deploy operator
oc apply -f subscription.yaml

Next, it is important to create a service account with the correct cluster rolebinding so the namespace configuration operator can have the authorization required to operate as needed.
Here, we create a namespace-config-superuser service account with cluster-admin permissions. This is done by:

# Create the service account
oc apply -f service-account.yaml

# Create the correct cluster rolebinding
oc apply -f cluster-rolebinding.yaml
