# personal-website
To create a single webpage and host it on Amazon S3, follow these steps:

1. Create your webpage:
   - Use HTML, CSS, and JavaScript to create your webpage.
   - Save the file as "index.html".

2. Set up an Amazon Web Services (AWS) account:
   - Go to aws.amazon.com and sign up if you don't have an account.

3. Create an S3 bucket:
   - Log in to the AWS Management Console.
   - Navigate to S3 service.
   - Click "Create bucket".
   - Choose a unique name for your bucket.
   - Configure bucket settings (leave defaults for most cases).
   - Enable "Static website hosting" under the Properties tab.

4. Upload your files:
   - In the S3 bucket, click "Upload".
   - Select and upload your "index.html" file and any other assets.

5. Set bucket policy for public access:
   - Go to the "Permissions" tab in your bucket.
   - Edit the Bucket Policy and add a policy to allow public read access.

6. Configure static website hosting:
   - In the "Properties" tab, find "Static website hosting".
   - Set "Index document" to "index.html".
   - Save the changes and note the endpoint URL.

7. Access your website:
   - Use the endpoint URL to view your hosted webpage.
