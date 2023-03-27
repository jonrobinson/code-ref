# Steps

Steps also described here:
https://vercel.com/guides/how-can-i-use-github-actions-with-vercel

### Instal Vercel CLI
```
npm i -g vercel
```

### Get The Vercel Organization ID
1. Go to the folder
2. Run the following:
```
vercel login
vercel link
```
3. Inside the generated .vercel folder, save the `projectId` and `orgId` from the project.json

### Create the Vercel Token
Described here: https://vercel.com/guides/how-do-i-use-a-vercel-api-access-token
In order for this to work one of the "owners" or "admins" on the account needs to create token in Vercel.
This token is on your personal account.
Go here: https://vercel.com/account/tokens
Example name: "GitHub Actions - [YOUR APP]"


### Add all the secrets to Github project
Github -> Project -> Settings -> Secrets (Left Nav) -> Actions
```
VERCEL_ORG_ID
VERCEL_PROJECT_ID
VERCEL_TOKEN
```

