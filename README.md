# Google Cloud Platform Workshop

This repository contains workshops as part of a presentation on Google Cloud
Platform. Use this README to follow along with the workshops. Sections will 
be added as we progress through the workshop.

## WORKSHOP: Setting up a project

### Description

In this workshop, you will create a Google Cloud Platform project. A project
organizes all your Google Cloud Platform resources.

### Set up Billing

1.  Navigate to [Cloud Console](https://console.cloud.google.com).
1.  Sign in with a personal or @cornell.edu account.
1.  If you already have an active Google Cloud Platform trial or credit, skip
    ahead to the "Environment" section.
1.  If you have not activated a free trial, you should see the following image:
    ![Free
    Trial](./doc/images/free-trial.png)
    If you would like, you can sign up for this free trial. Doing this will
    require a credit card for identification purposes.
1.  If you cannot or do not wish to activate the free trial, ask a Googler for a
    credit key and redeem it [here](https://console.cloud.google.com/education). _Make sure you are applying it to your @cornell.edu account!_
1.  If you have a partner, add them to your coupon's billing account as a Billing Account Administrator (Top-left menu -> Billing -> Add Members/Select a role -> Add). This will allow them to continue to the Environment section in their own console with their own project.

### Environment

You can choose to run this either in Cloud Shell __(recommended)__ or on your own machine. If you choose to run on your own machine, follow the additional instructions under "Using your own machine".

Navigate to Cloud Shell by clicking on the following button (outlined in red) in the Cloud Console:

![cloud shell](./doc/images/gcp-top-bar.png)

Clone this repository with the following command:

```sh
git clone https://github.com/TrevorEdwards/gcp-workshop
```

Navigate to the repository directory:

```sh
cd gcp-workshop
```

Run the following interactive utility to set up billing, API access, and authentication:

```sh
./bin/init-project
```

__NOTE:__ This utility requires Node.js.

If at any time you get stuck, re-run the command and skip the steps you have already done.

Don't worry if you don't completely understand what's happening here -- this is something you would normally do through the web UI. In essence, the script:
1. Creates a new project, which is where your application will live.
1. Links a billing account to the project, which allows you to use Google APIs.
1. Enables the Cloud APIs necessary for this workshop.
1. Creates a service account, which is essentially a Google account for your application, and allows it to access the APIs.
    * As part of this step, you'll download a key file. This key is used in lieu of a password for the account.
1. Instructs you to add the key to your environment, which allows your application to find it.

#### Using your own machine

Before doing the above, you'll need to download [`gcloud`](https://cloud.google.com/sdk/gcloud/) first. As an extra step, you'll need to login with:

```bash
gcloud auth login
```

You will also need to download and install [Node.js 8](https://nodejs.org).

After that, you should be all set to continue as if you were running in the Cloud Shell in the instructions above.

