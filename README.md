<a href="https://coderwall.com/rougin"><img alt="Endorse rougin on Coderwall" src="https://api.coderwall.com/rougin/endorsecount.png" /></a>

Slytherin
=========

Slytherin is a simple and extensible PHP library that follows an MVC software architectural pattern for creating small projects. Unlike the other frameworks that provides big libraries that you don't need in developing your web applications, this library utilizes [Composer](https://getcomposer.org) to add, update or even remove external libraries with ease.

Installation Instructions
============
1. This library requires [Composer](https://getcomposer.org) and [Git](http://git-scm.com) in order to get it work. Download and install the latest version of it first. The instructions for that can be found [here](http://git-scm.com/downloads) and [here](https://getcomposer.org/download/). If you have already installed Composer and Git on your system, then you can skip this step.
2. Create a new composer.json file and add the Slytherin package in your require-list in ```composer.json``` and then run ```composer install```:

  ```
  {
      "require": {
          "rougin/slytherin": "dev-master"
      }
  }
  ```
  
3. After the installation, run this command from the PHP CLI:

  For Unix and Mac:

  ```php vendor/bin/accio```
  
  For Windows or if there are no symbolic links found at ```vendor/bin``` directory:

  ```php vendor/rougin/slytherin/bin/accio```

4. Aaaand you're done! Try to experiment this library with other libraries that currently exists on [Packagist](https://packagist.org/) (or in [GitHub](https://github.com/search?utf8=%E2%9C%93&q=php+library)!) and create an awesome and cool PHP project! :smile:


Let's try it!
============

###Controller

1. Create a simple controller using your favorite text editor, name it Accounts.php and save it in the controllers folder. 
    ```
    class Accounts extends Slytherin\Controller
    {
        public function index()
        {
          return 'Hello World!';
        }

    }
    ```
    
2. Visit your site and it should display "Hello World!".

3. Make sure your controller extends the parent controller class so that it can inherit all its functions.

4. You could use ```use Slytherin\Controller as Controller;``` to shorten the call of the class.

###Model

1. Create a Account.php using your text editor and save it in the model folder.
    ```
    class Account
    {
        public function all()
        {
            $result = array(
                'Angel',
                'Rougin'
            );

            return $result;
        }
    }
    ```

2. Load your model in the Accounts.php controller constructor.
    ```
    public function __construct(\Account $Account)
    {

    }
    ```

3. To utilize your model, declare the following code in your index method or any method where you want to use it.
    ```
    $Account = new Account();

    $data['accounts'] = $Account->all();
    ```

4. To view the returned results refer to the *View* section.

###View

1. To load a particular view file, use the following function inside the method: 

    ```Slytherin\View::render('name of the view file', 'variable where the data is stored');```

2. You could use ```use Slytherin\View as View;``` to shorten the call of the class.