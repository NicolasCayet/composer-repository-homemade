# Homemade Composer Repository

### Use Satis : static Composer repository generator.
##### Find full tutorial from https://getcomposer.org/doc/articles/handling-private-packages-with-satis.md

1. Import Satis project in current directory ; Run :
```Batchfile 
php composer.phar create-project composer/satis --stability=dev
```
*Create satis/ directory containing Satis project*


#####After a while :
1. Write the `satis.json` file : it describes what is your repository and what it can trade

2. Run :
```Batchfile 
php satis/bin/satis build satis.json www/
```
Returns :
```Batchfile
[Composer\Repository\InvalidRepositoryException]
No valid composer.json was found in any branch or tag of git@github.com:NicolasCayet/repo-composer.git, could not load a package from it.
```
 
3. After creating and pushing a `composer.json` root file into repo-composer.git, build command works !
*Create www/ directory*


4. Create Apache virtual host for your Composer Repository; DocumentRoot set on previously created directory `www/`. This folder contains `packages.json` and it must be accessible though HTTP


5. Add a require-dev `justfortest/repo1` in our Client application's composer.json file


6. `composer install` and goal is achieved !

