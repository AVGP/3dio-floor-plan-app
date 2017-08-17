# 3d.io Floor Plan App

* Converts floor plans into [basic 3d models](https://3d.io/floor-plan-to-3d-conversion.html) using 3d.io APIs.
* Stores conversion related info in your database.
* Sends email notification to your cutomer when 3d model is ready.

## Install

### 1. **Deploy app to heroku by clicking this button:**

<a href="https://heroku.com/deploy?template=https://github.com/archilogic-com/3dio-floor-plan-app/tree/master">
  <img src="https://www.herokucdn.com/deploy/button.svg" alt="Deploy">
</a>

### 2. **Setup 3d.io, database and email:**

| Docs | Purpose | Url |
| --- | --- | --- |
| [Setup 3d.io](docs/3dio.md) | Floor plan conversion service | https://3d.io |
| [Setup firebase](docs/firebase.md) | Database service | https://firebase.com |
| [Setup sendGrid](docs/sendgrid.md) | Email service | https://sendgrid.com |
| | Public tunnel to your localhost for testing (optional) | https://ngrok.com |

### 3. **Set environment variables**

Name | Example | Notes
--- | --- | ---
PUBLIC_SERVER_URL | `https://your-server-url.com` | The URL where your server is publicly accessible. To obtain a public URL for local development use https://ngrok.com
EMAIL_FROM | `floor-plan@your-domain.com` | Emails to your customers will have this email address in the "from" field 
EMAIL_ADMIN | `admin@your-domain.com` | Email of the administrator responsible for this server. Error notifications will be send here.
3DIO_SECRET_API_KEY | `51ebcf63-d5d...` | Docs: [Setup 3d.io](docs/3dio.md)
SENDGRID_API_KEY | `SG.wBcemOAdRZ-yC-Zwz1ZhPw.uw5h5VhS...` | Docs: [Setup sendGrid](docs/sendgrid.md)
FIREBASE_PRIVATE_KEY | `-----BEGIN PRIVATE KEY-----\nMIIEvAIBADA...` | Docs: [Setup firebase](docs/firebase.md)
FIREBASE_CLIENT_EMAIL | `xyz@your-project-id.iam.gserviceaccount.com` | Docs: [Setup firebase](docs/firebase.md)
FIREBASE_DATABASE_URL | `https://your-project-id.firebaseio.com` | Docs: [Setup firebase](docs/firebase.md)

### 4. **Optional: Modify email messages to your customers in:**
* [api/convert-floor-plan-to-3d.js](https://github.com/archilogic-com/3dio-floor-plan-app/blob/master/api/convert-floor-plan-to-3d.js#L86)
* [api/on-conversion-status-update.js](https://github.com/archilogic-com/3dio-floor-plan-app/blob/master/api/on-conversion-status-update.js#L74)
