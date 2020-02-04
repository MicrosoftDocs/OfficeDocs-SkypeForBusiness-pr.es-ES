---
title: Definir y configurar un grupo de servidores front-end o un servidor Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ddc430370c59e279e0e36aa662da0f33973e0d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a>Definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-08_

Este procedimiento no requiere la pertenencia a un grupo de dominio de administrador o de privilegios local. Debe iniciar sesión en un equipo como usuario estándar.

Si está implementando un servidor empresarial, un número mínimo de servidores front-end de un grupo debe estar ejecutándose en todo momento. En la tabla siguiente se resumen estos requisitos.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Número total de servidores front-end en el grupo</th>
<th>Cantidad de servidores que es preciso que estén en ejecución para que el grupo funcione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1-2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>1</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>7-8</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>9-10</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>11-12</p></td>
<td><p>6</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Para Lync Server 2013, siempre que agregue o quite un servidor front-end de la agrupación, debe reiniciar los servicios. Quitar y agregar servidores se debe realizar como operaciones independientes. Por ejemplo, si va a agregar dos servidores front-end y quitar dos servidores front-end, use el siguiente proceso: 
> <OL>
> <LI>
> <P>Quite los dos servidores front-end.</P>
> <LI>
> <P>Publique y vuelva a activar la topología.</P>
> <LI>
> <P>Reiniciar los servicios</P>
> <LI>
> <P>Agregue los dos servidores front-end.</P>
> <LI>
> <P>Publique y vuelva a activar la topología.</P>
> <LI>
> <P>Reinicie los servicios.</P></LI></OL>



</div>

Una vez que haya definido su topología, use el siguiente procedimiento para definir un grupo de servidores front-end para el sitio. Para obtener más información sobre cómo definir la topología, consulte [definir y configurar una topología en el generador de topologías para Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).

<div>

## <a name="to-define-a-front-end-pool"></a>Para definir un grupo de servidores front-end

1.  En el Asistente para definir nuevo grupo front-end, en la página **definir el nuevo grupo front-end** , haga clic en **siguiente**.

2.  En la página **definir el FQDN del grupo de servidores front-end** , escriba un nombre de dominio completo (FQDN) para el grupo que está creando, haga clic en **Grupo front-end de Enterprise Edition**y, a continuación, haga clic en **siguiente**.

3.  En la página **definir los equipos de este grupo** , escriba un FQDN de equipo para el primer servidor front-end en el grupo y, a continuación, haga clic en **Agregar**. Repita este paso para todos los equipos adicionales (hasta doce) que desee agregar a la agrupación y, a continuación, haga clic en **siguiente**.

4.  En la página **seleccionar características** , seleccione las casillas de las características que desee en este grupo de servidores front-end. Por ejemplo, si va a implementar solo la mensajería instantánea (mi) y las características de presencia, debe activar la casilla **conferencias** para permitir la mensajería instantánea de varias personas, pero no seleccionar las casillas **Conferencia de acceso telefónico local (RTC)**, **telefonía IP empresarial**o **control de admisión de llamadas** , porque representan las características de conferencia de voz, vídeo y colaboración.
    
      - **Conferencia**   : esta selección permite un conjunto de características completo, entre las que se incluyen:
        
          - MENSAJERÍA instantánea con más de dos partes en una sesión de mensajería instantánea.
        
          - Conferencias, que incluye colaboración de documentos, uso compartido de aplicaciones y uso compartido de escritorio.
        
          - Conferencias a/V, que permite a los usuarios tener conferencias de audio y vídeo (A/V) en tiempo real sin necesidad de disponer de servicios externos, como el servicio Live Meeting o un puente de audio de terceros.
    
      - **Las conferencias**   de acceso telefónico local (RTC) permiten a los usuarios unirse a la parte de audio de una conferencia de 2013 de Lync Server mediante un teléfono con red telefónica conmutada (RTC) sin requerir un proveedor de servicios de audioconferencia.
    
      - **Enterprise Voice**   Enterprise Voice es la solución de voz sobre IP (VoIP) de Lync Server 2013 que permite a los usuarios realizar y recibir llamadas telefónicas. Puede implementar esta característica si piensa usar Lync Server 2013 para las llamadas de voz, el correo de voz y otras funciones que usan un dispositivo de hardware o un cliente de software.
    
      - **El CAC control de admisión de llamadas (CAC)**   determina, en función del ancho de banda de red disponible, si se permiten sesiones de comunicaciones en tiempo real, como las de voz o videollamadas que se pueden establecer. Si solo ha implementado la mensajería instantánea y la presencia, CAC no es necesario porque ninguna de estas dos características utiliza CAC.
    
      - **** El archivado de archivado le permite archivar contenido de mensajería instantánea, conferencias (reunión) o ambos que se envían a través de Lync Server 2013.   
    
      - ****   El servidor de supervisión de supervisión le permite recopilar datos numéricos que describan la calidad de los medios de su red y puntos de conexión, información de uso relacionada con llamadas VoIP, mensajes instantáneos, conversaciones a/V, reuniones, uso compartido de aplicaciones y transferencias de archivos, así como información sobre errores y solución de problemas para llamadas fallidas.
    
    <div>
    

    > [!NOTE]
    > Si desea habilitar CAC en su implementación, es necesario que habilite CAC en un solo grupo por sitio central. Se recomienda CAC si está implementando características de voz o conferencias A/V.

    
    </div>
    
    En la tabla siguiente se muestran las características disponibles (superior) y las funciones que se ofrecen a los usuarios (a la izquierda). Las selecciones de la tabla son lo que debe seleccionar para habilitar dichas características para su organización.
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th>Conferencias</th>
    <th>Conferencias de acceso telefónico local</th>
    <th>Telefonía IP empresarial</th>
    <th>Control de admisión de llamadas</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Mensajería instantánea y presencia</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p>Conferencias</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p>Conferencia A/V</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td><p>X</p></td>
    </tr>
    <tr class="even">
    <td><p>Telefonía IP empresarial</p></td>
    <td></td>
    <td></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    </tr>
    </tbody>
    </table>


5.  En la página **Seleccionar roles de servidor** colocados, puede Collocate el servidor de mediación en el servidor front-end o para implementarlo como servidor independiente.
    
    Puede Collocate el servidor de mediación en el grupo de servidores front-end.
    
      - Si tiene previsto Collocate el servidor de mediación en el grupo de servidores front-end Enterprise Edition, asegúrese de que la casilla está activada. El rol de servidor se implementará en los servidores del grupo.
    
      - Si tiene previsto implementar el servidor de mediación como un servidor independiente, desactive la casilla correspondiente. Implementará el servidor de mediación en un paso de implementación independiente después de implementar completamente el servidor front-end.
    
    <div>
    

    > [!NOTE]
    > Recomendamos que Collocate el servidor de mediación, si es posible. Para obtener más información sobre la compatibilidad de los servidores de mediación colocados o independientes, vea <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">componentes y topologías de servidor de mediación en Lync server 2013</A> en la documentación de planificación.

    
    </div>

6.  La página **asociar roles de servidor con este grupo de servidores front-end** le permite definir y asociar roles de servidor con el grupo de servidores front-end. Se encuentra disponible el siguiente rol:
    
    **Habilitar un grupo**   perimetral define y asocia un único servidor perimetral o un grupo de servidores perimetrales. Un servidor perimetral facilita la comunicación y la colaboración entre usuarios de la organización y las personas ajenas a esta, incluidos usuarios federados.
    
    Existen dos escenarios posibles que puede usar para implementar y asociar los roles de servidor:
    
    Para el escenario uno, se define una nueva topología para una nueva instalación. Puede enfocar la instalación de una de estas dos maneras:
    
      - Deje la casilla desactivada y continúe con la definición de la topología. Una vez que hayan publicado, configurado y comprobado los roles de los servidores front-end y back-end, puede volver a ejecutar el Generador de topologías para agregar los servidores de roles a la topología. Esta estrategia le permitirá probar el grupo de servidores front-end y el servidor que ejecuta SQL Server sin complicaciones adicionales de roles adicionales. Una vez completada la prueba inicial, puede volver a ejecutar el Generador de topologías para seleccionar los roles que necesite implementar.
    
      - Seleccione los roles que necesita instalar y, luego, configure el hardware para hospedar los roles seleccionados.
    
    En el escenario dos, tiene una implementación existente y su infraestructura está lista para los nuevos roles o necesita asociar los roles existentes con un nuevo servidor front-end:
    
      - En este caso, deberá seleccionar los roles que pretende implementar o asociar con el nuevo servidor front-end. En cualquier caso, continuará con la definición de los roles, la configuración de cualquier hardware necesario y procederá con la instalación.

7.  En la página **definir la tienda SQL** , realice una de las siguientes acciones:
    
      - Para usar el almacén de SQL Server existente que ya se ha definido en la topología, seleccione una instancia del **Almacén de SQL**.
    
      - Para definir una nueva instancia de SQL Server para almacenar la información del grupo, haga clic en **nuevo** y, a continuación, especifique el **FQDN de SQL Server**en el cuadro de diálogo **definir nueva tienda SQL** .
    
      - Para especificar el nombre de una instancia de SQL Server, seleccione **Instancia con nombre** y, luego, especifique el nombre de la instancia.
    
      - Para usar la instancia predeterminada, haga clic en **Instancia predeterminada**.
    
      - Para usar la creación de reflejos de SQL, seleccione **Habilitar reflejo SQL** y seleccione una instancia existente o cree una nueva.

8.  En la página **definir el recurso compartido de archivos** , realice una de las siguientes acciones:
    
      - Para usar un recurso compartido de archivos ya definido en la topología, seleccione **Usar un recurso compartido de archivos ya definido**.
    
      - Para definir un nuevo recurso compartido de archivos, seleccione **Definir un nuevo recurso compartido de archivos** en el cuadro **FQDN del servidor de archivos**, escriba el FQDN del servidor de archivos existente donde se ubicará el recurso compartido de archivos y, luego, escriba un nombre para el recurso compartido de archivos en el cuadro **Recurso compartido de archivos**.
    
    <div>
    

    > [!IMPORTANT]
    > El recurso compartido de archivos de Lync Server 2013 no se puede encontrar en el servidor front-end. Tenga en cuenta que en este ejemplo, el recurso compartido de archivos se ha ubicado en el servidor back-end basado en SQL Server. Es posible que no sea una ubicación óptima para los requisitos de la organización, y un servidor de archivos puede ser una mejor opción. Puede definir el recurso compartido de archivos sin que se haya creado el recurso compartido de archivos. Tendrá que crear el recurso compartido de archivos en la ubicación que defina antes de publicar la topología.

    
    </div>

9.  En la página **especificar la dirección URL de los servicios web** , siga uno de estos procedimientos o ambos:
    
    <div>
    

    > [!IMPORTANT]
    > La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.

    
    </div>
    
    <div>
    

    > [!WARNING]
    > Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único. Por ejemplo, si define el FQDN de los servicios web externos de un servidor front-end como <STRONG>pool01.contoso.com</STRONG>, no puede usar <STRONG>pool01.contoso.com</STRONG> para otro grupo de servidores front-end o servidor front-end.

    
    </div>
    
    1.  Si está configurando el equilibrio de carga de DNS, active la casilla **invalidar el FQDN del grupo de servicios Web interno** , escriba la dirección URL de base interna (que debe ser diferente de la del FQDN\<del grupo y\>podría ser, por ejemplo, la dirección URL base) en la **dirección URL base interna**.
        
        <div>
        

        > [!WARNING]
        > Si decide omitir los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único de cualquier otro grupo de servidores front-end, director o grupo de directores. <STRONG>Utilice únicamente caracteres estándar</STRONG> (incluyendo A–Z, a–z, 0–9 y guiones) al definir direcciones URL o nombres de dominio completos. No utilice caracteres Unicode ni de subrayado. Los caracteres no estándar en una dirección URL o un FQDN a menudo no son compatibles con DNS externos y CA públicas (es decir, cuando la dirección URL o el FQDN deben asignarse al nombre de sujeto o al nombre alternativo de sujeto en el certificado).

        
        </div>
    
    2.  De manera opcional, escriba la dirección URL de base externa en **dirección URL de base externa**. Debe escribir la dirección URL básica externa para diferenciarla del nombre de dominio interno. Por ejemplo, el dominio interno es contoso.net, pero el nombre de dominio externo es contoso.com. Definiría la dirección URL con el nombre de dominio contoso.com. También es importante en el caso de un proxy inverso. El nombre de dominio de la dirección URL base externa sería el mismo que el nombre de dominio del FQDN del servidor proxy inverso. La mensajería instantánea y la presencia requieren acceso HTTP al grupo de servidores front-end.
    
    <div>
    

    > [!NOTE]
    > Para usar el equilibrio de carga de DNS, debe crear los registros DNS adecuados. Para obtener más información, vea <A href="lync-server-2013-configure-dns-for-load-balancing.md">configurar DNS para el equilibrio de carga en Lync Server 2013</A>.

    
    </div>

10. Si seleccionó **conferencias** en la **página seleccionar características** , en la página **seleccionar un servidor de Office Web Apps** , seleccione **asociar grupo con un servidor de Office Web Apps** y, a continuación, haga clic en **nuevo** (o seleccione un servidor de Office Web Apps existente de la lista desplegable).

11. En el cuadro de diálogo **Definir nuevo Office Web Apps Server**, escriba el nombre de dominio completo (FQDN) del equipo de Office Web Apps Server en el cuadro **FQDN de Office Web Apps Server**; al hacerlo, la dirección URL de descubrimiento de Office Web Apps Server deberá aparecer automáticamente en el cuadro **Dirección URL de descubrimiento de Office Web Apps Server**.
    
    Si Office Web Apps Server está instalado en local y en la misma zona de red que Lync Server 2013, la opción **Office Web Apps Server se implementa en una red externa (es decir,** no se debe seleccionar el perímetro o la Internet).
    
    Si Office Web Apps Server está implementado fuera del firewall interno, seleccione la opción **Office Web Apps Server se implementa en una red externa (esto es, perimetral/Internet)**.
    
    <div>
    

    > [!NOTE]
    > Para obtener más información, vea <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">configurar la integración con Office Web Apps Server y Lync server 2013</A>.

    
    </div>

12. En la página **definir la tienda SQL de archivado** , seleccione una instancia existente o SQL Server, o bien defina una nueva instancia para almacenar los datos asociados con el archivado de datos.

13. En la página **definir la supervisión de la tienda SQL** , seleccione una instancia existente o SQL Server, o bien defina una nueva instancia para almacenar los datos asociados con la supervisión de datos.

14. Haga clic en **Siguiente**. Si definió otros servidores de roles en la página **asociar roles de servidor con este grupo de servidores front-end** , se abrirán las páginas del Asistente para configuración de roles para que pueda configurar los roles de servidor. Para obtener más información, vea lo siguiente:
    
    [Implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md)

15. Si no ha seleccionado roles de servidor adicionales para configurar e implementar, o cuando haya finalizado la configuración de los servidores de roles adicionales, haga clic en **Finalizar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

