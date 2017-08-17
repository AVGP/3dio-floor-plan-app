# 3d.io Floor Plan App

* Converts floor plans into [basic 3d models](https://3d.io/floor-plan-to-3d-conversion.html) using 3d.io APIs.
* Stores conversion related info in your database.
* Sends email notification to your cutomer when 3d model is ready.

## Install

### 1. **Deploy app to heroku by clicking this button:**

<a href="https://heroku.com/deploy?template=https://github.com/archilogic-com/3dio-floor-plan-app/tree/master">
  <img src="https://www.herokucdn.com/deploy/button.svg" alt="Deploy">
</a>

### 2. **Setup services:**


* [**3d.io**](docs/3dio.md) - Floor plan conversion service
* [**firebase**](docs/firebase.md) - Database service
* [**sendGrid**](docs/sendgrid.md) - Email service
* [**ngrok.com**](https://ngrok.com) - Public tunnel to your localhost for testing (optional)

### 3. **Set environment variables**

Name | Notes
--- | ---
**PUBLIC_SERVER_URL** | The URL where your server is publicly accessible. To obtain a public URL for local development use https://ngrok.com<br>Example: `https://your-server-url.com`
**EMAIL_FROM** | Emails to your customers will have this email address in the "from" field<br>Example: `floor-plan@your-domain.com`
**EMAIL_ADMIN** | Email of the administrator responsible for this server. Error notifications will be send here.<br>Example: `admin@your-domain.com`
**3DIO_SECRET_API_KEY** | [Setup 3d.io](docs/3dio.md), Example: `51ebcf63-d5d...`
**SENDGRID_API_KEY** | [Setup sendGrid](docs/sendgrid.md), Example: `SG.wBcemOAdRZ-yC-ZwzVhS...`
**FIREBASE_PRIVATE_KEY** | [Setup firebase](docs/firebase.md), Example: `-----BEGIN PRIVATE KEY-----\nMIIIBADA...`
**FIREBASE_CLIENT_EMAIL** | [Setup firebase](docs/firebase.md), Example: `xyz@project-id.iam.gserviceaccount.com`
**FIREBASE_DATABASE_URL** | [Setup firebase](docs/firebase.md), Example: `https://your-project-id.firebaseio.com`

### 4. **Optional: Modify email messages to your customers in:**
* [api/convert-floor-plan-to-3d.js](https://github.com/archilogic-com/3dio-floor-plan-app/blob/master/api/convert-floor-plan-to-3d.js#L86)
* [api/on-conversion-status-update.js](https://github.com/archilogic-com/3dio-floor-plan-app/blob/master/api/on-conversion-status-update.js#L74)
