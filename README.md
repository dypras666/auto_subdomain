# auto_subdomain codeigniter

    $dot        = '.'; 
    $satu       = stripos($_SERVER['HTTP_HOST'], $dot);
    $offset     = $satu + 0; 
    $dua        = stripos ($_SERVER['HTTP_HOST'], $dot, $offset);  
    $first_two  = substr($_SERVER['HTTP_HOST'], 0, $dua); 

    switch ( $_SERVER['HTTP_HOST'] ) {
    case $first_two.'.namadomain.com':
        $route['default_controller'] = $first_two;
        $route['(:any)'] = $first_two.'/$1';

    break;
    default:
        $route['default_controller'] = 'home';
    break;
    }
