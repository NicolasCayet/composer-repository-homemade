# Homemade Composer Repository

### Use Satis : static Composer repository generator.
##### Find full tutorial from https://getcomposer.org/doc/articles/handling-private-packages-with-satis.md

- Import Satis project in current directory ; Run :
```Batchfile 
php composer.phar create-project composer/satis --stability=dev
```
*Create satis/ directory containing Satis project*


#####After a while :
- Write the `satis.json` file : it describes what is your repository and what it can trade

- Run :
```Batchfile 
php satis/bin/satis build satis.json www/
```
Returns :
```Batchfile
[Composer\Repository\InvalidRepositoryException]
No valid composer.json was found in any branch or tag of git@github.com:NicolasCayet/repo-composer.git, could not load a package from it.
```
 
- After creating and pushing a `composer.json` root file into https://github.com/NicolasCayet/repo-composer, build command works !
*Create www/ directory*


- Create Apache virtual host for your Composer Repository; DocumentRoot set on previously created directory `www/`. This folder contains `packages.json` and it must be accessible though HTTP


- Add a require-dev `justfortest/repo1` in our Client application's composer.json file


- `composer install` and goal is achieved !

