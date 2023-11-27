# MVP Deployment for AsciiArtify
After successfully completing the PoC, the "AsciiArtify" team is ready to move on to deploying the MVP.

[![asciicast](https://asciinema.org/a/yy60kU7ssLYizHjWx11OMPhGw.svg)](https://asciinema.org/a/yy60kU7ssLYizHjWx11OMPhGw)

The MVP is a minimal product with essential features needed to validate the product with a focus group of users. At this stage, developers add additional features, fix bugs, and enhance the product based on user feedback.

From the DevOps perspective, it is necessary to create an application in ArgoCD that will track the Git repository of the product https://github.com/den-vasyliev/go-demo-app and configure automatic synchronization.

After successfully configuring ArgoCD, you can initiate a full cycle to demonstrate how ArgoCD automatically tracks and synchronizes changes from the Git repository and deploys them to the Kubernetes cluster.

The task's outcome will be a brief demo in the project repository demonstrating how the application works, deployed using the infrastructure you configured.

You can find an example configuration in the Coding Session video.

To fulfill the task, provide a link to the AsciiArtify repository with an embedded demo showcasing the product's functionality on the infrastructure you set up (File doc/MVP.md in Markdown format, on the main branch).

```bash
wget -O /tmp/g.png https://www.freepnglogos.com/uploads/google-logo-png/file-google-logo-svg-wikimedia-commons-23.png
ls -la /tmp/
curl -F 'image=@/tmp/g.png' localhost:8088/img/
```
