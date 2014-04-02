##### Homemade Composer Repository

### Use Satis : static Composer repository generator.
## Find full tutorial from https://getcomposer.org/doc/articles/handling-private-packages-with-satis.md

1. Run "php composer.phar create-project composer/satis --stability=dev" to import Satis project in current directory


#After a while :
2. Run "php satis/bin/satis build satis.json www/"

2.1 Returned :
	[Composer\Repository\InvalidRepositoryException]                                                                                           
	  No valid composer.json was found in any branch or tag of git@github.com:NicolasCayet/repo-composer.git, could not load a package from it.
2.2 After creating and pushing a composer.json root file into repo-composer.git, build command works ! => Create www/ directory


3. Create Apache virtual host for your Composer Repository; DocumentRoot set on previously created directory `www/`


4. Add a require-dev `justfortest/repo1` in our Client application's composer.json file

4.1 Client composer.phar install does not work (`justfortest/repo1 not found`) without registering our composer repo

