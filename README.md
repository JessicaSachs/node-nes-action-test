## Minimal Reproduction and Example Project for Node NES GitHub Action

This project is being used to test the HeroDevs NES support for End-of-Life versions of Node when installed via GitHub action.
See the [documentation](https://docs.herodevs.com/node/nodejs).

### Testing the GHA
1. Relies on `act` to verify GitHub actions locally, so [install it](https://nektosact.com/installation) if necessary and start up your Docker daemon 🐳.
2. Make a `.secrets` file based off of `.secrets.example`

**Example `.secrets` file:**
```
NES_REGISTRY_TOKEN=your_token_here
```

3. Run the following command to attempt to pull the Node NES image.
```sh
act -s NES_REGISTRY_TOKEN="$(cat .secrets | grep NES_REGISTRY_TOKEN | cut -d '=' -f2)"
```

> If you are suspicious that your secrets aren't being properly passed through to the action, you can place an `echo` before the above command.
