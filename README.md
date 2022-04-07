# Github actions webhook trigger

Trigger a github action on a simple POST request like this curl :

```bash
curl -XPOST -u "[username]:[token]" \
  -H "Accept: application/vnd.github.everest-preview+json" \
  -H "Content-Type: application/json" \
  https://api.github.com/repos/[username]/[repo]/dispatches \
  --data '{"event_type": "[your-event-type]"}'
```
### Setup


You will have to replace some of the values in your CURL requests : 


Key | Value
------------ | -------------
token | Your Github personal access token ([Create personal token with repo rights](https://github.com/settings/tokens/new), there is [a tutorial](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)).
username | Your Github username
repo | Your Github repo where you will trigger the github action
your-event-type | Your event-type used in your [workflow yml](.github/workflows/trigger.yml)



Here's an example for this repo to trigger the github action: 

```
curl -XPOST -u "Tharushan:ghp_fACErabYlsBdFNMdjIUhTvBjwxIjMVtvDCsF" \
  -H "Accept: application/vnd.github.everest-preview+json" \
  -H "Content-Type: application/json" \
  https://api.github.com/repos/Tharushan/github-actions-webhook/dispatches \
  --data '{"event_type": "webhook-trigger"}'
```