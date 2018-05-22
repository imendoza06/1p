1p - GIT WORKFLOW CHEATSHEET
master = production branch
Start on master branch 
	#clone repository 
 git clone https://github.com/imendoza06/1p.git
cd 1p  /
cd server/
		npm install
	cd ../client/ 
		npm install
Step 1: Create a new branch to work on - feature branch
# a. Create a new feature branch
		git branch im_new_feature_name
	# b. Checkout your new feature branch
		git checkout im_new_feature_name 
		OR 
# a&b. Checkout and Switch to your new feature branch
		git checkout -b im_new_feature_name 
Step 2: Write some code, and commit your code regularly
	# Add all files to the stage
		git add . OR git add <file_name>
	# Commit files 
		git commit -m "Message about this commit"
	# Optional (but recommended) push local branch to remote
		git push origin im_feature_name
Step 3: Am I finish making changes? 
	If NO!, continue working on the feature and committing your changes… step 2.
	If YES!, move to step 4.
Step 4: Fetch from remote when you are done 
	# Run fetch to make sure you’re up to date when merging changes back into master
		git fetch
Step 5: Squash your commits and get ready to merge -- rebase all your changes into one commit
# Open the interactive rebase tool
		git rebase -i origin/master
		#Vim - squash all commits into one 
		:wq!
Step 6: Check out and Pull from master branch
# Checkout the master branch
	git checkout master
# Pull from master branch 
git pull origin master

*Test code before pulling or merging 
***CODE REVIEW STARTS*** 

Step 7: Merge and push your changes 
# Merge jc_feature_name INTO master
		git merge im_feature_name
# Push your local master branch to remote 
		git push origin master
Step 8: Clean Up! Once changes have been merged, delete your feature branches 
# Delete remote feature branch (the colon is important!)
		git push origin :im_feature_name
	# Delete local branch
		git branch -d im_feature_name
Step 9: Start over with new awesome feature because you are awesome! :)
