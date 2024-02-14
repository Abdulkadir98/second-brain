 1.  Tell me about a time when you had a conflict with a co-worker
     One of our systems requires to download a file from S3 which was failing non-deterministically. There was an issue with the class responsible for downloading it, I wanted to get a feature out (impatient) so I argued that if the failures are less maybe we can live with it. A senior engineer on the team vehemently disagreed saying that we absolutely cannot have any failures in production. If we are failing jobs then we are doing something really wrong. I understood then how naive I was and later we figured out a more robust way to fetch files.

 2.  Tell me about a time in which you had a conflict and needed to influence somebody else.
     - mentoring an intern, they had an idea to use S3 but I felt S3 is not the right solution. So asked the intern to bring it for dicussion to the rest of the team. The team agreed that DDB would be a better solution to store columnar data than s3 and then the intern was convinced.
 
 3.  What was the most difficult bug that you fixed in the past 6 months? 
       A part of our system requires to fetch items from Dynamo DB. If the query is null then it returns an empty map. Our code did not account for that and fetched key on it which didn't exist throwing an NPE. Deep dived into the issue and later discovered buried somewhere in documentation that DDB returns an empty Map. Then accounted for that so that we do not see NPE in code.
      