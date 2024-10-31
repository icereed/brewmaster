# Brewmaster for Klarstein Brauheld Smart

Welcome to the Brewmaster app for Klarstein Brauheld Smart! This Docker image is designed for hobby brewers who want a seamless and enjoyable brewing experience. Our user-friendly application, crafted with React and Go, lets you effortlessly manage your brewing sessions. Here’s how to get started!

## Introduction

Our app connects directly with the Klarstein Brauheld system via the Tuya IoT platform, allowing for programmable control of your brewing process. With just a few setups, you can begin brewing like a pro!

## Prerequisites

Before diving in, ensure you have Docker installed on your computer. If you haven’t installed it yet, you can download it from [Docker's official site](https://docs.docker.com/get-docker/).

You’re correct; linking your Tuya app account to the cloud project is crucial to have any device in the app show up in the cloud project and be accessible for integration.

## Setup Guide

### Pairing the Klarstein Brauheld with Tuya

1. **Install the Tuya App:** Download and install the Tuya app on your smartphone (not the Klarstein app).
2. **Create a Tuya Account:** Sign up for a new account within the app.
3. **Activate Pairing Mode:** On your Klarstein Brauheld, hold the reset button for 5 seconds to enter pairing mode.
4. **Add Device:** In the Tuya app, select "Add Device" -> "Others" -> "Others (Wi-Fi)".
5. **Link App Account to Cloud Project:**
   - Log in to the [Tuya IoT Development Platform](https://iot.tuya.com/) with the same account used in the Tuya app.
   - **Create a Cloud Project**: Choose "Smart Home" as the project type.
   - **Authorize APIs**: Enable APIs like "IoT Core" for device interaction.
   - **Link the Tuya App Account**: Within the project settings, select "Link Tuya App Account," scan the displayed QR code with the Tuya app on your phone (found under “Me > Account and Security > Link with Tuya IoT Platform Account”), and confirm.
6. **Retrieve Credentials:**
   - **Access ID and Key**: After creating the project, you’ll find your **Access ID** and **Access Key** in the project’s "Authorization Key" section under "Overview."
   - **Device ID**: Find your Device ID by going to the device settings in the Tuya app, selecting "Device Information," and noting the displayed Device ID.

## Running the Application

To launch the app, execute the following command in your terminal.
Be sure to replace `<your tuya access id>`, `<your tuya access key>`, and `<your tuya device id>` with your actual Tuya credentials.

```bash
docker run -p 8080:8080 -e TUYA_ACCESS_ID="<your tuya access id>" -e TUYA_ACCESS_KEY="<your tuya access key>" -e TUYA_DEVICE_ID="<your tuya device id>" icereed/brewmaster
```

This command will start the Brewmaster application and make it accessible at port 8080 on your host machine.

## Accessing the Application

After starting the Docker container:

- **Open a Web Browser:** Navigate to [http://localhost:8080](http://localhost:8080).
- **Begin Brewing:** Explore the application and start your brewing adventure!

## Enjoy Brewing!

Questions? Join the discussions and get tips on the [original forum thread](https://hobbybrauer.de/forum/viewtopic.php?p=519277).

Happy brewing!

## Bonus: Screenshot

![Screenshot](./images/screenshot.png)
