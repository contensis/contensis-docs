If you want to use a private docker registry with Blocks you will need to provide the appropriate credentials to authenticate to your registry. Contensis supports Azure, DockerHub and GitHub private repositories.

To configure your credentials, you must be a System Administrator.

1.  Navigate to **Settings** from the sidebar.
2.  Select **General** settings.
3.  Under the *Blocks* section, toggle **Enable private registry** to on.
4.  Press the **Add** button and select your registry provider (Azure, DockerHub, or GitHub).
5.  Enter your username and an access token with at least read permissions.
6.  Save your changes.

Once configured, Blocks will use these credentials to download your Docker image.