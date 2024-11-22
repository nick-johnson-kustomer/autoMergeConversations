# autoMergeConversations
This workflow will automatically merge new conversations with existing open conversations, created by Nick Johnson.

When a new email conversation is created (conversation X), this workflow will look up the most recent open email conversation for the same email address (conversation Y) and then merge conversation X into conversation Y. 

# IMPORTANT NOTE
While this workflow is designed to automatically merge conversations, it is NOT RECOMMENDED to automatically merge conversations. Merges can not be undone, so it can be very risky to set up any automations like this. Use this at the risk of your own data. That said, this is a demonstration of how it could be done.

# Workflow steps
Step 1 - the workflow triggers on message creation.

Conditional step - this checks tha tthe message channel is email and that the direction type is initial-in.

Step 2 - an API call to the search endpoint which looks up open email conversations from the same email address. Make sure to update the org name in the URI and also make sure to have an appropriate API key in the workflow variables to us in the headers.

Step 3 - this regex step isolates the top conversation ID.

Conditional step - this checks if a conversation ID was found in step 3.

Step 4 - this step merges the new conversation from step 1 into the conversation found in step 2 (and isolated by step 3).
