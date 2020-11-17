# No Anti-CSRF tokens were found in a HTML submission form.



Una solicutud falsa entre sitios en un ataque que compromete y obliga a una víctima a 
enviar su solicitud HTTP a un destino objetivo sin su conocimiento o intención para poder 
realizar una acción como víctima. La causa oculta es la funcionalidad de la aplicación 
utilizando acciones de URL/formulario que pueden ser adivinados de forma repetible. 
La naturaleza del ataque es que CSRG explota la confianza que un sitio web proporciona a un usuario. 
Por el contrario, las cadenas de comandos de los sitios cruzados (XSS) explotan la confianza 
que un usuario proporciona en un sitio web. Al igual que XSS, los ataques CSRG no son de 
forma necesaria de sitios cruzados, pero hay la posibilidad de que si pueden serlo. La f
alsificación de las solicitudes ente los sitios también se conoce como CSRF, XSRG, ataques 
con un solo clic, montaje de sesión, diputado confundido y navegación en alta mar.

Los ataques de CSRG son muy efectivos en varias situaciones, que incluyen:
*La victima tiene una sesión activa en el sitio de destino.
    *La víctima se autoriza por medio de la autenticación HTTP en el sitio de destino.
    *La víctima se encuentra en la misma red local que el sitio de destino.

CSRF se ha utilizado especialmente para poder realizar una acción contra un sitio objetivo utilizando 
los privilegios de la víctima, pero se han revelado técnicas recientes para difundir información 
al obtener el acceso a la respuesta. El riesgo de divulgación de información aumenta de forma drástica 
cuando el sitio de destino se encuentra vulnerable a XSS, porque XSS se puede utilizar como una plataforma 
para CSRF, lo que le permite al atacante que opere desde adentro de los líites de la misma política de origen.


Solución
--------

Origina un nonce único para cada uno de los formularios, coloque el nonce en el formularo y confirme la 
independencia al obtener el formulario. Asegúrese de que el nonce no sea predecible (CWE-330).
Usted tiene que tener en cuenta que esto puede pasar desapercibido utilizando XSS.

Identificar las operaciones que sean especialmente peligrosas. Cuando el usuario desarrolla una 
operación peligrosa, envíe una solicitud de confirmación de forma separada para poder garantizar que 
el usuario tenga la intención de desarrollar esa operación.
Usted tiene que tener en cuenta que esto puede pasar desapercibido utilizando XSS.

Utilice el control de gestión de la sesión de ESAPI.
Este control introduce un elemento para CSRF.

No utilice el método GET para ninguna de las solicitudes que puedan desencadenar un cambio de estado.

Fase: Implementación
Revise que la solicitud se creó en la página esperada. Esto podría quebrar la funcionalidad auténtica, 
ya que los usuarios o los representantes puede ser que hayan desactivado el envío de Referer por motivos 
`[de privacidad.