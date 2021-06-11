# Identity and Access Management (IAM)
[On Your console > IAM & Admin](https://console.cloud.google.com/iam-admin/iam)
IAM lets you grant granular access to specific Google Cloud resources and helps prevent access to other resources. IAM lets you adopt the security principle of least privilege, which states that nobody should have more permissions than they actually need.
## IAM Roles
[On Your console > IAM & Admin > Roles](https://console.cloud.google.com/iam-admin/roles)
Roles are permissions. You cannot grant a permission to the user directly. Instead, you grant them a role.
### Basic Roles
- Viewer: Read Only on all gcp resources
- Editor: Read + Edit actions on all gcp resources
- Owner: Read + Edit actions on all gcp resources + Manage roles + Billing
**Recommended**: Don't use in production
### Predefined roles
Fine-grained roles predefined and managed by Google.
- Admin
- Creator
- Viewer
### Custom Roles
When predefined roles are **not** sufficient, you can create your own roles
## Policy
Assign permissions to members, map a roles, members and conditions
## Policy Troubleshooter
[On Your console > IAM & Admin > Policy Troubleshooter](https://console.cloud.google.com/iam-admin/troubleshooter)
Check if the api call will grant the principal access to a resource.
## Service Accounts
[On Your console > IAM & Admin > Service Accounts](https://console.cloud.google.com/iam-admin/serviceaccounts)
A service account is an account for an application instead of an individual end user. When you run code that's hosted on Google Cloud, the code runs as the account you specify.Can't login via browser
### Default service Account
### User Managed
Recommended
### Google-managed service accounts
Created and managed by google
## Google Group
[On Your console > IAM & Admin > Groups](https://console.cloud.google.com/projectselector2/iam-admin/groups)
A Google group is a named collection of Google Accounts and service accounts. Every Google group has a unique email address that's associated with the group. You can find the email address that's associated with a Google group by clicking About on the homepage of any Google group. For more information about Google Groups, see the Google Groups homepage.
## CLI
List Roles: `gcloud iam roles list`
Describe Role: `gcloud iam roles describe my-role`
List service Accounts: `gcloud iam service-accounts list`
List Roles of SVC: `gcloud iam service-accounts get-iam-policy  my-iam-account@my-project.iam.gserviceaccount.com`
Update IAM Policy of SVC: `gcloud iam service-accounts add-iam-policy-binding  my-iam-account@my-project.iam.gserviceaccount.com  --member='user:test-user@gmail.com' --role='roles/editor'`
Simulator: `gcloud iam simulator replay-recent-access projects/project-id  path/to/policy_file.json`
Test Permissions: `gcloud iam list-testable-permissions  //cloudresourcemanager.googleapis.com/organizations/1234567`
[Full Documentation](https://cloud.google.com/sdk/gcloud/reference/iam)