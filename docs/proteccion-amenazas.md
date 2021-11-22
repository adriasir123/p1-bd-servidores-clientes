# Protección contra amenazas (+ coste).

**Incendios**

 * Detectores y alarmas de humo.
 
 * Sistema de gases inertes que tiene dos formas de actuar para suprimir dos tercios del triángulo de fuego (combustible, comburente y energía de activación):
 
    * Ante una detección de subida de temperatura, que se considere peligrosa, libera halocarbonos que contribuyen a disipar el calor afectando a la energía de activación, en este caso, que es una alta temperatura.

 
    * Cuando los detectores de humo se activen, este sistema libera un gas inerte como el Árgon y este desplaza el oxígeno elimando el comburente de dicho triángulo.
    ![Apagafuegos](https://www.missioncriticalmagazine.com/ext/resources/MC/2020/07-08_July-August/Fire-Suppression-Fig2-900x550.jpg)

    * Un ejemplo de la distribución de este sistema:
    ![Sistema](https://www.siex2001.com/sites/default/files/imagecache/foto-info-sistemas/sistemas/imagenes/salainertes.jpg)

 * Activación de scripts de resguardo de información. 

 * Revisiones periódicas de toda la instalación eléctrica, así como el sistema de extinción y detección de incendios.

 * Control de todas las obras y trabajos que puedan realizarse en el entorno de
la empresa para evitar posibles accidentes por manejo de materiales inflamables o uso de herramientas que puedan generar chispas.


**Accesos no autorizados al CPD**

 * Un sistema de alarma que sirva tanto para los momentos de ausencia del personal, así como una activa por si intentan acceder posibles intrusos y den una respuesta rápida a las autoridades. A tener en cuenta el refuerzo de potenciales puntos de acceso como puertas y ventanas.

 * Puerta de acceso a la sala de servidores con blindaje y que incluya un sistema biómetrico, un modelo bastante interesante a este tipo de acceso es el de doble verificación (huella y un pin); además incluye una pequeña cámara que realiza una foto al ser usado, aportando una seguridad extra.

 ![Imagen de ejmplo](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse2.mm.bing.net%2Fth%3Fid%3DOIP.yxvwoprNGes-TtYsAp8OawHaHa%26pid%3DApi&f=1)

 * Cámaras de seguridad interiores (cpd) en combinación con algunas perimetrales para tener controlado el recinto de la empresa. Importante que las cámaras tengan capacidad de captar imágenes en entornos de baja luminosidad.


**Interrupciones suministro eléctrico**

 * SAIS, que permitan mantener los servidores encendidos el tiempo suficiente para activar la generación de copias de respaldo, alertas a los administradores y llegado a un periodo duradero de no poder recuperar el suministro, organizar un apagado controlado de los servidores.
 
 * Generador de gasolina, es un complemento para los SAIS en caso de momentos extremos y que su principal ventaja es que alarga más el tiempo de margen para recueperar la energía principal.


**Averías en la electrónica**

 * RAID en combinación a discos duros de repuesto, contribuirán a que no haya pérdida de datos para los clientes.

 * Otros componentes de repuesto como fuentes de alimentación, memoria RAM, cableado, switches y routers de repuesto.
 
 * Para casos más extremos de averías, la alta disponibilidad y el servicio estaría garantizado entre local y la conmutación con AWS.


**Secuestro de datos (Ransomware)**

 * Copias de respaldo de manera periódica.
 
 * Uso de escáneres de vulnerabilidades sobre los equipos y los servidores para reforzar posibles puntos débiles.
 
 * Una política de mantener el software lo más actualizado posible, dentro de lo estable, y estar al tanto de los posibles arreglos de seguridad que vayan publicando los canales oficiales.
 
 * Formación y concienciación de los trabajadores en posibles fallos que se pueden cometer y los potenciales peligros a los que se puede someter una empresa de esta índole.


**Robo de dispositivos móviles**

 * Uso de algoritmos de encriptación para proteger la información que puedan disponer.
 
 * Junto a lo primero, concienciar a los trabajadores para que tengan la menor cantidad de información crítica disponible en dichos dispositivos y realicen copias de seguridad de los mismos.
 
 * Uso de aplicaciones de rastreo y bloqueo.


**Suplantación de identidad (Phishing)**

 * Formación de los trabajadores en la materia.
 
 * Habilitar en el Firewall de la empresa una lista negra con páginas comunes de phishing, integración de una herramienta antiphishing en los navegadores y en el cliente de correo electrónico añadir direcciones mail potencialmente peligrosas, reportadas por la comunidad o canales oficiales.
 
 * Añadir una "pregunta secreta", en la que se pregunta una información que sólo debe ser conocida por el usuario y la empresa para garantizar que ese contenido está verificado como seguro.


**Compromiso de contraseñas**

 * Igual de importante que en otros puntos, la formación a los trabajadores es un vector importante para minimizar el riesgo humano.

 * Cambiar contraseñas regularmente.
 
 * Acceso con pares de claves como medida complementaria.

 * Uso de herramientas de fortaleza de contraseñas, para garantizar que no son vulnerables a ataques de fuerza bruta o  que no se encuentran dentro de los diccionarios de claves que circulan por internet. 


**Explotación de vulnerabilidades (Exploits)**

 * Aplicar parches de seguridad a medida que se vayan distribuyendo en las fuentes oficiales, así como mantener actualizado el software en uso.

 * Desinstalar complementos del navegador que no esten autorizados.
 
 * Tener solamente los puertos necesarios abiertos y los que estén abiertos, siempre controlados.

 * Tener un control de la aplicaciones especializadas creadas por los trabajadores o por un proveedor externo.

 * Instalar cortafuegos, escaneo de vulnerabilidades o aplicaciones de protección en puntos de frontera (SNORT con reglas que identifiquen), tener un punto bastión entre la red interna e internet.

 
**Ataques de denegación de servicio (DoS)**

 * Uso de balanceadores de carga en conjunción a los cortafuegos.
 
 * ACLs para controlar el flujo de tráfico en las subredes en caso de ataques internos.
 
 * Usar redes CDN (cloudflare).
 
 * Aumentar el ancho de banda en caso de que los filtros previos no retengan la totalidad de los ataques, un plan de escalado.
 
 * Implementar a nivel del servidor protecciones contra ataques de denegación de servicio distribuido (DDoS) como el que realizan las redes de bots.