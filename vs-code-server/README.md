# code-server is VS Code, accessible through the browser, rootless

## Running on a Heroku container stack

```sh
HASHED_PASSWORD=$(printf "thisismypassword" | sha256sum | cut -d' ' -f1)

heroku apps:create \
    --stack container \
    --region=${HEROKU_REGION:-eu} \
    ${HEROKU_APP}

heroku config:set HASHED_PASSWORD=$HASHED_PASSWORD
```
