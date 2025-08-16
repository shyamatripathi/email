## Environment Variables
Create a `.env` file in the root directory based on `.env.example`:
EMAIL_USER=your_email@example.com
EMAIL_PASS=your_smtp_password

## Running Locally
Start the API locally with:
npx serverless offline
Or specify a custom port:
npx serverless offline --httpPort 4000
Your local endpoint will be available at http://localhost:4000/dev/send.

## API Endpoint
POST /dev/send
Request Body:
{
  "receiver_email": "recipient@example.com",
  "subject": "Hello from Serverless",
  "body_text": "This is a test email."
}
Success Response (200):
{
  "message": "Email sent successfully"
}
Error Response (400/500):
{
  "error": "Error description here"
}

## Deployment to AWS
sls deploy
This will create the Lambda function, API Gateway endpoint, and necessary resources on AWS.

## Gmail App Password Setup
If you are using Gmail as your SMTP provider:
1. Enable 2-Step Verification in your Google Account.
2. Go to Security > App Passwords.
3. Create a new app password for "Mail".
4. Use that generated password in your `.env` file as `EMAIL_PASS`.

## License
MIT
