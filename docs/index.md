
# Technical Documentation

This is the official technical documentation of the *Guinea Insurance Third Party Motor Insurance*.
Any Developer looking to contribute to this project is expected to **THOROULY READ THIS BRIEF DOCUMENTATION** first.

If he/she makes any contribution towards the project, they are expected to update this documentation before lauching.

### Tools and Packages
> PHP 7
>
> Laravel 5.7 
>
> Javascript/J-Query
>
>[ Spatie - Laravel Roles and Permissions](https://github.com/spatie/laravel-permission).


 
## Getting Started

**To get started on the project, strictly follow the following steps:**

>> Clone Repository/Pull latest version of the repository

>> Run ``composer install``

>> If you don't have a `.env` file already, Do cp `.env.example` .env

>> Configure `.env` file as well as the files in the config folder to suite your needs


>> If you already have a database table, drop all the tables in the database else create a database for the project with name `motorthirdpary`

>> Run `php artisan migrate`
 
>> Run `php artisan guinea:setup-roles-and-permissions`

>> Run `composer dump-autoload`

>> Run `php artisan db:seed`

>> Do `php artisan cache:forget spatie.permission.cache` to clear permissions cache whenever you make changes in the permissions and roles tables in the database. 

## Project layout
The project follows the conventional Laravel layout with the following styles:
>All admin controllers and views are in `Controllers/Admin` and `views/admin` (except the auth files which are in the controller and views root of both).
>
>All agent controllers and views are in Controllers root folder and `views/user` folder.
>
> The list of roles and permissions are located in `app/Guinea`
>

## Before You Contribute
>> We are targetting older browsers and as such all Javascript written should be carefully checked for Backwards compatibility with browsers as far as IE 8. If however such JS is to be used, a suitable polyfill should be written.

>> Proper consideration and care should be taken before editing or deleting someone else's code.

>> Follow the style of variable declaration already existing and only install non-buggy composer dependencies.


## Creating a New Agent or Admin
The process uses the `Admin/AddNew` controller to perform this act. The view is in the `admin/addnew.blade.php` file.
The controller uses a substantial amount of JS files to perform some of its searching and filtering.
Pagination is done using `jquery datatables`

## Deleting, Activation and Deactivation of Agents or Admins
This also uses the `Admin/AddNew` controller to perform its action. For deleting, all user details are removed permanently.
The `toggleOnlineStatus` merely toggles the value in the column `flagged` which is in the `users` table. This is used for preventing users who are flagged from performing transactions on the portal.

## Searching For Agent or User
This functionality uses jquery to perform its actions.
