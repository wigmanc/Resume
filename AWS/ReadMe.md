- AWS
    - This guide is just my documentation with my notes and roadblock. For an in depth tutorial AWS documentation will provide with everything.
    
    [Tutorial: Configuring a static website on Amazon S3]
    (https://docs.aws.amazon.com/AmazonS3/latest/userguide/HostingWebsiteOnS3Setup.html)
    
![blob](https://github.com/wigmanc/Resume/blob/c846cd3b230c7771877124f76c12979706d08d7a/AWS/1.png)

    - The basis of the website is to be secure yet straightforward, and with that in mind, I choose to have an S3 Bucket that blocks all public access Off and with Static website hosting enabled—then attached SSL certificate to secure it.

![Static Website](https://github.com/wigmanc/Resume/blob/master/AWS/2.png)

    - I could have my resume online with just this, but it would not be secure. To add security, I have attached an SSL certificate. I used AWS Certificate Manager, keeping in mind that the region is set to N. Virginia.
    - For validation had issues with DNS CNAME as my domain is not configurable through AWS Route53, so I opted out for email validation. Keep in mind that AWS will send the email to the following: [admin@yourdomain.com](mailto:admin@yourdomain.com), [administrator@yourdomain.com](mailto:administrator@yourdomain.com), [hostmaster@yourdomain.com](mailto:hostmaster@yourdomain.com), [postmaster@yourdomain.com](mailto:postmaster@yourdomain.com), [webmaster@yourdomain.com](mailto:webmaster@yourdomain.com).
    - After certificates are verified and approved, you create your CloudFront distribution in which you will get your URL that you will point to your DNS as a CNAME record.
    - In the end we have an S3 bucket static website distributed trough CloudFront with SSL certs attached. For a future project current visits to resume website are being logged to another S3 bucket.
    - All documentation for CloudFront can be found at https://aws.amazon.com/premiumsupport/knowledge-center/analyze-logs-athena/
Flow of things with this AWS setup.

![Example](https://github.com/wigmanc/Resume/blob/master/AWS/3.png)
