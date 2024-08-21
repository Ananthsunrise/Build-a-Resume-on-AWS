# Build-a-Resume-on-AWS

In this project, you can build a resume throuh aws. for that you only need your html,css and js files from chatgpt or your own.

AWS Services used : 
1.AWS S3
2.AWS ROUTE53
3.AWS Certificate Manager
4.AWS CloudFont

Procedure : 
1.Go to s3->create one bucket->upload your code files in s3->disable block all public access option->enablestatic website hosting->add attached bicket policy to allow your bucket content public->now copy your static website link and paste in new tab.  your static website is ready.

2.Now we need to add custom domain name for our static website.
  Go to route53->create hosted zone ->create record by select a record type->select alias and select s3 bucket endpoint
  Now type you can access static website by using your custom domain name(for ex: mywebapp.com)
  
3.Finally we need to make our static website with high security https. for that we need to request certificate and create cloudfont distribution.
  Go to aws certificate manager->reauest certificate->select public certificate->enter our custom domain name->select dns validation - >click request
  Go to aws certificate manager->create record in route53 under domain section
  Go to CloudFont-> create distribution->slect s3 static websit domain name ->select use website endpoint - >select redirect http to https option under viewer ->select a 
 created certificate->create distribution
  (now copy the link after creating distribution and paste in new tab. you can see website with https security. But we actually need https security for our custom domain so 
 we need to update record A i  route 53)

4.Go to Route53->Select A record ->Click edit -> Select cloudfont distribution and update A record.
  Now our static website for resume  with https security by our custom domain name.
