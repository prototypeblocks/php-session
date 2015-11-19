# php-session  

## getting started  
``` 
include 'Session.php';  
use Prototypeblocks\Session;  
``` 
## examples  
#### init
``` 
Session::init();
// Will start / initialise a session. (eq: session_start();)
``` 
#### get
``` 
$session = Session::get();
// $session contains full $_SESSION array
``` 
``` 
$session = Session::get('user');
// $session contains $_SESSION['user'] value
``` 
``` 
$session = Session::get('user', 'email');
// $session contains $_SESSION['user']['email'] value
``` 
Session::get can go as deep into an array as you want, just by adding more parameters.     
#### set    
Last parameter is the value that will be set. 
All parameters before that will move one level deeper into the array.
``` 
Session::set('title', 'Readme');
// Session contains array('title' => 'Readme')
``` 
``` 
Session::set('meta', 'title', 'Readme');
// Session contains 
array(
'meta' => array(
  'title => 'Readme', 
);
``` 
``` 
$array = (0 => 'a', 1 => 'b', 2 => 'c');
Session::set('meta', $array);
// Session contains 
array(
'meta' => array(
  0 => 'a',
  1 => 'b',
  2 => 'c'
);
``` 
#### destroy
``` 
Session::destroy();
// Destroy session (eq: session_destroy();)
``` 
