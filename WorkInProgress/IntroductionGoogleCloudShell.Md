# Introduction to Google Cloud Shell and commands list

#### Introduction

[Google Cloud Shell](https://cloud.google.com/shell) is a Google Cloud Platform interactive shell interface. It allows you to manage your projects and resources directly from the browser, without the need to install the Google Cloud SDK or any other tools on your computer.

A variety of utilities are already installed in the online Cloud Shell Editor such as Bash, GCP SDK, Nano, Composer, Git, Docker and many more.

**Slash your cloud costs by 30%**

**With support for more than 50+ cloud services, Economize's Recommendations helps cloud infrastructure teams like yours to cut cloud costs like a pro.**

Start Saving

Try the Sandbox

The online Cloud Shell can be used to develop, test, debug, and deploy cloud-based instances. App development can be performed from the browser itself, and a host of different options are available for users to optimize their processes.





## Activate and use GCP Cloud Shell



- Sign in to your [Google Cloud Console](https://console.cloud.google.com/)



## ![img](https://i0.wp.com/blog.economize.cloud/wp-content/uploads/2022/02/Activate-Google-Cloud-Shell-.png?resize=300%2C98&ssl=1)

- Go to the top navigation bar, and click the square button at the right of the search bar. A highlighted text pops up with the words `Activate Cloud Shell`

![img](https://i0.wp.com/blog.economize.cloud/wp-content/uploads/2022/02/Cloud-Shell-Terminal-min.png?resize=692%2C203&ssl=1)

- A terminal window is presented after a few seconds. Your Cloud Shell is now ready to use. You already have a small instance Google Compute Engine virtual machine running a Debian-based Linux operating system when Cloud Shell is activated. If left unused for over an hour, the instance is automatically terminated.

![img](https://i0.wp.com/blog.economize.cloud/wp-content/uploads/2022/02/CLoud-Shell-Terminal-View-Projects-List.png?resize=761%2C213&ssl=1)

- Type `gcloud projects lists` in the terminal to view a list of all the available GCP environments associated with your account. If you are doing this for the first time, an identity authorization prompt appears, simply click ‘Authorize’ to proceed.
- If you have multiple projects visible, you can type `gcloud set project <#Project ID#>` in the terminal and control that specific project.

![img](https://i0.wp.com/blog.economize.cloud/wp-content/uploads/2022/02/Cloud-Shell-Clone-Repository.png?resize=607%2C160&ssl=1)

For more in-depth documentation on the different functionalities of Google Cloud Shell, you can access the GCP [documentation](https://cloud.google.com/shell/docs).



## **Google Cloud Shell Commands List**

## 

Here is a list of the basic  commands to get you started with the Cloud Shell CLI.

\1)   **List the active account name**

```
gcloud auth list
```

\2)  **List the project ID**

```
gcloud config list project
```

\3)   **Create a new instance using Gcloud shell**

```
gcloud compute instances create [INSTANCE_NAME] --machine-type n1-standard-2 --zone [ZONE_NAME]
```

\4)   **SSH into the machine**

```
gcloud compute ssh [INSTANCE_NAME] --zone [YOUR_ZONE]
```

\5)   **Create a Storage bucket**

```
gsutil mb gs://[BUCKET_NAME]
```

\6)   **Copy a file in to the bucket**

```
gsutil cp [FILE_NAME] gs://[BUCKET_NAME]
```

\7)   **List the compute engine instances created:**

```
gcloud compute instances list
```

\8)   **Stop a Compute Instance**

```
gcloud compute instances stop [INSTANCE-NAME]
```





## ![img](https://i0.wp.com/blog.economize.cloud/wp-content/uploads/2022/02/image-13.png?resize=712%2C401&ssl=1)

## Overview

Google Cloud Shell is a wonderful package than allows you to manage your GCP resources with the flexibility of a Linux shell. Being able to interface with your resources on any remote browser offers an advanced level of accessibility. Having a host of different yet essential tools already pre-installed and updated saves a lot of time and efforts. Finally, having options to work on multiple instances simultaneously massively increases productivity, enabling users to maintain multiple workflows and collaborate with different teams from the same platform.

### *Related*

[Google Cloud Certifications – A Beginner’s Guide](https://blog.economize.cloud/gcp-certifications/?relatedposts_hit=1&relatedposts_origin=24&relatedposts_position=0&relatedposts_hit=1&relatedposts_origin=24&relatedposts_position=0&relatedposts_hit=1&relatedposts_origin=24&relatedposts_position=0&relatedposts_hit=1&relatedposts_origin=24&relatedposts_position=0)March 23, 2022

[How to get free Google Cloud Platform (GCP) Credits](https://blog.economize.cloud/free-google-cloud-credits/?relatedposts_hit=1&relatedposts_origin=24&relatedposts_position=1&relatedposts_hit=1&relatedposts_origin=24&relatedposts_position=1&relatedposts_hit=1&relatedposts_origin=24&relatedposts_position=1&relatedposts_hit=1&relatedposts_origin=24&relatedposts_position=1)March 14, 2022

[GCP Spot VM: Introduction and how to use them?](https://blog.economize.cloud/introduction-gcp-spot-instances/?relatedposts_hit=1&relatedposts_origin=24&relatedposts_position=2&relatedposts_hit=1&relatedposts_origin=24&relatedposts_position=2&relatedposts_hit=1&relatedposts_origin=24&relatedposts_position=2&relatedposts_hit=1&relatedposts_origin=24&relatedposts_position=2)October 20, 2021