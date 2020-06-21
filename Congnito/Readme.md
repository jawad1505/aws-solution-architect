# Web Identity Federation
  * gives a user access after they have authenticated with a web based provider i.e. Facebook, google and amazon
  * on success, user receives an authentication code from web ID provider, which they can trade for temporary AWS security credentials

# Cognito
  * brokers between the app and facebook or Google to provide temp credentials which map to an IAM role allowing access for AWS
  * is a Web Identity Federation
  * sign up and sign in to your apps
  * Access for guest users
  * acts as an identity broker between your apps and web id providers, so you dont need to write any additional code.
  * Synchronizes user data for multiple devices
  * recommended for all mobile apps AWS services
  
  
# Cognito User Pools: 
  * user directories used to manage signup and signIn for mobile and web apps
  * user can sign in directly in user pool using facebook/google/amazon
  * Successful authenticaton generates a JSON Web Token (JWT)

# Identity Pool:
  * enable provides temp access to AWS services like S3 or dynamo DB 
  * where as user pools are actual users i.e. email,passord where user pool is granting access to resources
  
 # Example:
 1: USer goes to USER POOL which checks credentials from Social Media
 2: AWS cerdentials are verified from USER POOLS for type of access
 3: USER are granted JWT to access AWS resources
 
 
 * Tracks which device was used to access, use SNS for notifications
