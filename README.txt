URL: https://udacity.veraenterprises.io
Cloudfron URL: http://dpjx06znb1t0r.cloudfront.net



I configured the s3 bucket so that the files would not be public and would only be visible from the cloudfront. 

For this I configured the policy in this way:
{
    "Version": "2012-10-17",
    "Statement: [
        {
            "Sid": "2",
            "Effect": "Allow",
            "Main": {
                "AWS": "arn:aws:iam::cloudfront:user/CloudFront Origin Access Identity ERHNH7LUFRLZN"
            },
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::udacity-website-202008242208/*"
        }
    ]
}



I set up my own domain in a dns and in Cloudfront.
I also had to configure a certificate in ACM to use it in Cloudfront with my domain.

