---
title: 'Lync Server 2013: Configuración de los servidores proxy inversos'
TOCTitle: Configuración de los servidores proxy inversos
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48274229
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de los servidores proxy inversos para Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Para las implementaciones del servidor perimetral de Microsoft Lync Server 2013 se requiere un proxy inverso HTTPS en la red perimetral para que los clientes externos puedan acceder a los servicios web de Lync Server 2013 (denominados *componentes web* en Office Communications Server) en el director y el grupo principal del usuario. Algunas de las características que requieren un acceso externo a través de un proxy inverso incluyen lo siguiente:

  - Habilitación de los usuarios externos para descargar el contenido de la reunión para sus reuniones.

  - Habilitación de los usuarios externos para expandir grupos de distribución.

  - Habilitación de los usuarios remotos para descargar archivos desde el servicio de libreta de direcciones.

  - Acceso al cliente de Lync Web App.

  - Acceso a la página web de configuración de conferencia de acceso telefónico local.

  - Habilitación de los dispositivos externos para conectarse al servicio web de actualización de dispositivos y obtener actualizaciones.

  - Habilitación de aplicaciones móviles para detectar automáticamente y usar las direcciones URL de movilidad (Mcx) en Internet.

  - Habilitación del cliente de Lync 2013, Aplicación de la Tienda Windows de Lync y el cliente móvil de Lync 2013 para ubicar las direcciones URL de Lync Discover (detección automática) y usar API web de comunicaciones unificadas (UCWA).

Se recomienda configurar el proxy inverso HTTP para publicar todos los servicios web en todos los grupos. Si se publica https:// *ExternalFQDN* /\*, se publican todos los directorios virtuales de IIS para un grupo. Se necesita una regla de publicación para cada servidor Standard Edition, cada Grupo de servidores front-end o cada Director o Grupo de directores de la organización.

Además, deberá publicar las direcciones URL sencillas. Si la organización tiene un Director o un Grupo de directores, el proxy inverso HTTP escucha las solicitudes HTTP/HTTPS para direcciones URL sencillas y las envía al directorio virtual de servicios web externos del Director o Grupo de directores. Si no se ha implementado ningún Director, deberá designar un grupo para administrar las solicitudes para las URL sencillas. (Si este no es el grupo principal del usuario, las redireccionará a los servicios web del grupo principal del usuario). Las direcciones URL sencillas pueden administrarse mediante una regla de publicación web dedicada, o bien puede agregarlas a los nombres públicos de la regla de publicación web para el Director. También debe publicar la dirección URL externa del servicio Detección automática.

Puede usar Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1 o Internet Information Server 7.0, 7.5 o 8.0 con enrutamiento de solicitud de aplicaciones (IIS ARR) como proxy inverso. Los pasos que se detallan en esta sección describen cómo configurar Forefront Threat Management Gateway (TMG) 2010. Los pasos para configurar ISA Server 2006 son casi idénticos. También se proporciona asistencia para IIS ARR. Si usa un proxy inverso distinto, consulte la documentación de ese producto y asigne los requisitos definidos aquí a las características asociadas en otros proxies inversos.

> [!IMPORTANT]  
> El enrutamiento de solicitud de aplicaciones de Internet Information Server (IIS ARR) es una opción compatible y totalmente probada para implementar un proxy inverso para Lync Server 2010 y Lync Server 2013. En noviembre de 2012, Microsoft dejó de vender licencias de Forefront Threat Management Gateway 2010 o TMG. TMG sigue siendo un producto totalmente compatible y sigue disponible para su venta en aparatos vendidos por terceros. Además, muchos firewalls y equilibradores de carga de hardware de terceros dan soporte para proxies inversos. Para saber cuáles son los firewalls y los equilibradores de carga de hardware con características de proxy inverso, pídale a su proveedor las instrucciones para configurar su producto y poder dar soporte de proxy inverso en Lync Server. También puede consultar a los terceros que han enviado documentación para su producto a Microsoft. Los terceros ofrecen soporte para sus soluciones. Para ver cuáles son los terceros activos en el suministro de soluciones, vea <a href="http://go.microsoft.com/fwlink/?linkid=268730">Infraestructura cualificada para Microsoft Lync</a>.



Los siguientes temas y procedimientos usan Forefront Threat Management Gateway 2010 e IIS ARR como la base para los procedimientos de implementación y configuración.

  - [Configurar los nombres de dominio completos (FQDN) de la granja de servidores web para Lync Server 2013](lync-server-2013-configure-web-farm-fqdns.md)

  - [Configurar adaptadores de red en Lync Server 2013](lync-server-2013-configure-network-adapters.md)

  - [Solicitar y configurar un certificado para el proxy HTTP inverso en Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [Configurar las reglas de publicación web para un solo grupo de servidores interno en Lync Server 2013](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [Comprobar o configurar la autenticación y la certificación en directorios virtuales IIS en Lync Server 2013](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [Crear registros DNS para servidores de proxy inverso en Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [Comprobar el acceso a través del proxy inverso en Lync Server 2013](lync-server-2013-verify-access-through-your-reverse-proxy.md)

## Antes de comenzar

Para implementar Forefront Threat Management Gateway 2010 como su proxy inverso, tiene que instalar y configurar un servidor con los requisitos previos y los requisitos de hardware, definidos en la documentación de Forefront Threat Management Gateway 2010. Vea el siguiente conjunto de temas para configurar correctamente el hardware e instalar Forefront Threat Management Gateway 2010 en el servidor antes de continuar.

  [Forefront Threat Management Gateway (TMG) 2010](http://go.microsoft.com/fwlink/?linkid=291292)  

  [Recomendaciones de hardware para Forefront TMG 2010](http://go.microsoft.com/fwlink/?linkid=291293)  

Si desea implementar correctamente IIS ARR como proxy inverso, revise los siguientes temas para configurar el hardware y el software necesario.

  Para instalar IIS en Windows Server 2008 o Windows Server 2008 R2, consulte el tema sobre [instalación de IIS 7 en Windows Server 2008 o Windows Server 2008 R2](http://go.microsoft.com/fwlink/?linkid=291296)  

  Para instalar IIS en Windows Server 2012, consulte el tema sobre [instalación de IIS 8 en Windows Server 2012](http://go.microsoft.com/fwlink/?linkid=291297)  

  Para instalar IIS en Windows Server 2012 R2, vea [Cómo instalar IIS 8.5 en Windows Server 2012 R2](http://go.microsoft.com/fwlink/?linkid=330687)  

  Para descargar la extensión de enrutamiento de solicitud de aplicaciones para IIS, siga las instrucciones en la página de [descarga de enrutamiento de solicitud de aplicaciones v2.5](http://go.microsoft.com/fwlink/?linkid=291298)  

  Para instalar ARR, siga las instrucciones en la página de [instalación de enrutamiento de solicitud de aplicación versión 2](http://go.microsoft.com/fwlink/?linkid=291299)  
    

  > [!NOTE]
  > Las instrucciones publicadas actualmente son para ARR 2.0. No hay diferencia en la instalación de la extensión para ninguna de las dos versiones.


