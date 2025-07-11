// update data option 1
        // $car = Car::find(1);
        // $car -> price = 1000;
        // $car -> save();

        // update data option 2
        // Car::updateOrCreate(
        //     ['id' => '1'], 
        //     ['price' => 15000] /** or variable */
        // );

        // mass update
        // Car::where('published_at', null)
        //     ->where('user_id', 1)
        //     ->update(['published_at' => now()]);
        
		
Execution Policy(This is temporary and only applies to the current session)

	Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass

	npm install && npm run build
	
Git Commands

	git init
	git add . or *
	git commit -m "First Commit"
	git remote add origin [repo link]
	git push -u origin [branch]
	git push origin HEAD:master
	git clone [repo link]
	git fetch 
	git switch
	git merge
	git rebase [branch] --interactive
	git pull
	git branch -d
	npm run build
	git add dist -f
	git commit
	git subtree push --prefix dist origin [branch]
	git log --oneline
	git revert [id]
	git remote remove origin
	
	cat .git/config  # save your <github-uri> somewhere
	rm -rf .git
	
Laravel Local Env Setup
	
	composer install
	# Set .env file
	php artisan migrate
	php artisan key:generate
	php artisan storage:link
	php artisan serve
	