# Ricardo
Base8
<?php ?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Proyecto de Base de Datos</title>
</head>
<body>
<table border='1' width="1500px" height="690px">
	<tr>
		<td>
        Header
        <?php 
		class Generador
{
        static private $instancia = NULL;
private function __construct(){}    
static public function getInstancia() 
{
   if (self::$instancia == NULL) {
      self::$instancia = new Generador ();
   }
return self::$instancia;
}
 
function palabras($min = 4, $max = 8)
{		
	$vocales 	= array('a', 'e', 'i', 'o', 'u');
	$consonantes 	= array('b', 'c', 'd', 'f', 'g', 'j', 'l', 'm', 'n', 'p', 'r', 's', 't');
	$tamano 	= intval(rand($min, $max));
	$actual		= intval(rand(1,2));		
	$nombre 	= '';	
	for($x=0;$x<$tamano;$x++)
	{			
		if($actual == 0)
		{
			$actual	= 1;
			$pos 	= rand(0,count($vocales)-1);
			$nombre	.=  $vocales[$pos];				
		}
		else			
		{
			$actual	= 0;
			$pos 	= rand(0,count($consonantes)-1);
			$nombre	.=  $consonantes[$pos];				
		}				
	}
	return ucfirst($nombre);
}
}
	?>
	</td>
	</tr>
    <tr>
    	<td>
        <table>
          <tr>
          <td>
        <label>Nombre de la base de datos</label>
        </td>
         <td>
            <input />
          </td>
        </tr>
        <tr>
        <td>
                <br />
        <label>Nombre de la tabla</label>
        </td>
        </tr>
        <tr>
            <td>
             <input />
             </td>
        </tr>
        <tr>
             <td>
             <br />
             <input type="submit"; value="Agregar Fila"/>
              </td>
        </tr>
        </table>
        </td>
    </tr>
   <tr>
			<td>
       				<table>
                    		<tr>
                            	<td>
                                <div>
                                <label>Orden</label>
                                </div>
                                </td>
                                <td>
                                <div>
                               <label>Nombre Dato</label>
                                </div>
                                </td>
                                <td>
                                 <div>
                                <label>Tipo de Dato</label
                                ></div>
                                </td>
                                <td>
                                 <div>
                                <label>Eliminar</label
                                ></div>
                                </td>
                            </tr>
                            <tr>
                            	<td>
                                <label>
                                1
                                </label>
                                </td>
                                <td>
                                <input />
                                </td>
                                <td>
                                <select>
                                <option>Seleccione una Opción</option>
                                <option>Nombre</option>
                                <option>Apellido</option>
                                <option>Telefono</option>
                                <option>Edad</option>
                                <option>Email</option>
                                <option>Municipio</option>
                                <option>Pais</option>
                                </select>
                                </td>
                                <td>
       <input name="eliminar" type="radio" value="" />
                                </td>
                            </tr>
       				</table>
			</td>
	</tr>
    	<tr>
			<td>
            <?php
			 $i = 1;
			while($i<=30){
        $generador = Generador::getInstancia();
echo $generador->palabras();
echo '<br/>';
// Posibles salidas: Jose, Pablo, Pedro, Camila, Leceme, Nodi (Entre otras miles	
$i++;		
  }
?>
<table>
<?php

?>
</table>
			</td>
	</tr>
</table>
</body>
</html>

