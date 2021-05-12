![ConfigCat Logo](/docs/resources/configcat_logo.svg)

# ConfigCat

[ConfigCat](https://configcat.com/) is a feature flag service for teams. It allows you to enable/disable features remotely without redeploying code. ConfigCat is cross-platform and works with your web, mobile, and server-side applications. Key features include basic flags, targeting, %-based rollouts, variations, multiple environments, A/B testing, permissions, team management, SSO, 2FA, and SDKs for 10+ platforms.

## Example Layerfile

```
FROM vm/ubuntu:18.04
RUN curl -sL https://deb.nodesource.com/setup_12.x | bash
RUN apt install nodejs
COPY . .
RUN npm install
SECRET ENV CONFIGCAT_AUTH_KEY
RUN curl "https://api.configcat.com/v1/products/dcd53ddb-8104-4e48-8cc0-5df1088c6113/environments" \
    -X POST \
    -u $CONFIGCAT_AUTH_KEY \
    -H "Content-Type: application/json" \
    -d '{"name": "layerci-'$LAYERCI_JOB_ID'"}'
RUN BACKGROUND REACT_CONFIGCAT_ENV="layerci-$LAYERCI_JOB_ID" npm run start
EXPOSE WEBSITE localhost:3000
```

### Setting up ConfigCat with LayerCI

Using a Layerfile like the one above creates a ConfigCat environment. For more information on how to set up ConfigCat, check out their [documentation pages](https://configcat.com/docs/getting-started/).
