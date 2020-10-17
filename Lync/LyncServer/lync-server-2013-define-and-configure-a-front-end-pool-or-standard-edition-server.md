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
ms.openlocfilehash: 847aeda66657b2bd665964d6fec3276dc22807ea
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531517"
---
# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a>Definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-08_

Este procedimiento no requiere pertenencia al grupo de dominio con privilegios o de administrador local. Deberá iniciar sesión en un equipo como usuario estándar.

Si va a implementar un servidor de empresa, debe ejecutarse en todo momento un número mínimo de servidores front-end en un grupo. En la tabla siguiente, se resumen estos requisitos.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Número total de servidores front-end en el grupo</th>
<th>Número necesario de servidores en ejecución para que el grupo sea funcional</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1-2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>segundo</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>7-8</p></td>
<td><p>4 </p></td>
</tr>
<tr class="odd">
<td><p>9-10</p></td>
<td><p>5 </p></td>
</tr>
<tr class="even">
<td><p>11-12</p></td>
<td><p>6 </p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Para Lync Server 2013, siempre que agregue o quite un servidor front-end del grupo de servidores, debe reiniciar los servicios. La eliminación y la adición de servidores se deben realizar como operaciones independientes. Por ejemplo, si va a agregar dos servidores front-end y quitar dos servidores front-end, use el siguiente proceso: 
> <OL>
> <LI>
> <P>Elimine los dos servidores front-end.</P>
> <LI>
> <P>Publique y reactive la topología.</P>
> <LI>
> <P>Reinicie los servicios</P>
> <LI>
> <P>Añada los dos servidores front-end.</P>
> <LI>
> <P>Publique y reactive a topología.</P>
> <LI>
> <P>Reinicie los servicios.</P></LI></OL>



</div>

Una vez que haya definido la topología, use el siguiente procedimiento para definir un grupo de servidores front-end para el sitio. Para obtener más información sobre cómo definir la topología, consulte [definir y configurar una topología en Topology Builder para Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).

<div>

## <a name="to-define-a-front-end-pool"></a>Para definir un grupo de servidores front-end

1.  En el Asistente para definir nuevo grupo de servidores front-end, en la página **Definir nuevo grupo de servidores front-end**, haga clic en **Siguiente**.

2.  En la página **definir el FQDN del grupo de servidores front-end** , escriba un nombre de dominio completo (FQDN) para el grupo que va a crear, haga clic en **grupo de servidores front-end Enterprise Edition**y, a continuación, haga clic en **siguiente**.

3.  En la página **definir los equipos de este grupo** , escriba un FQDN de equipo para el primer servidor front-end del grupo y, a continuación, haga clic en **Agregar**. Repita este paso para todos los equipos adicionales (hasta un máximo de doce) que desee agregar al grupo de servidores y, a continuación, haga clic en **siguiente**.

4.  En la página **Seleccionar características**, active las casillas de las características que desee en este grupo de servidores front-end. Por ejemplo, si va a implementar sólo las características de mensajería instantánea (mi) y presencia, active la casilla de verificación **Conferencia** para permitir la mensajería instantánea de varios participantes pero no activar las casillas **Conferencia de acceso telefónico local (RTC)**, **telefonía IP empresarial**o **control de admisión de llamadas** , ya que representan características de conferencia de voz, vídeo y colaboración.
    
      - **Conferencia**     Esta selección habilita un amplio conjunto de características, entre las que se incluyen:
        
          - Mensajería instantánea con más de dos interlocutores en una sesión de mensajería instantánea
        
          - Conferencias, lo que incluye colaboración en documentos, uso compartido de aplicaciones y uso compartido de escritorio
        
          - Conferencia a/V, que permite a los usuarios tener conferencias de audio y vídeo (A/V) en tiempo real sin necesidad de servicios externos, como el servicio de Live Meeting o un puente de audio de terceros.
    
      - Conferencias de acceso **telefónico local (RTC)**     Permite a los usuarios unirse a la parte de audio de una conferencia de Lync Server 2013 mediante un teléfono de red telefónica conmutada (RTC) sin necesidad de un proveedor de servicios de audioconferencia.
    
      - **Telefonía IP empresarial**     Enterprise Voice es la solución de voz sobre IP (VoIP) en Lync Server 2013 que permite a los usuarios realizar y recibir llamadas telefónicas. Implementaría esta característica si planea usar Lync Server 2013 para llamadas de voz, correo de voz y otras funciones que usan un dispositivo de hardware o un cliente de software.
    
      - **Control de admisión de llamadas (CAC)**     El CAC determina, en función del ancho de banda de red disponible, si se permite que se establezcan sesiones de comunicaciones en tiempo real, como las llamadas de voz o vídeo. Si solo ha implementado mensajería instantánea y presencia, no necesita el CAC, ya que ninguna de estas características lo usa.
    
      - **Archivado**     El archivado proporciona una forma de archivar contenido de mensajería instantánea, contenido de conferencias (reuniones) o ambos que se envían a través de Lync Server 2013.
    
      - **Supervisión**     El servidor de supervisión permite recopilar datos numéricos que describen la calidad de los medios en la red y los extremos, la información de uso relacionada con las llamadas de VoIP, los mensajes de mensajería instantánea, las conversaciones A/V, las reuniones, el uso compartido de aplicaciones y las transferencias de archivos, así como la información de errores y solución de problemas de llamadas fallidas.
    
    <div>
    

    > [!NOTE]
    > Si desea habilitar el CAC en la implementación, es preciso habilitarlo exactamente en un grupo de servidores por sitio central. El CAC se recomienda si está implementando características de voz o conferencia A/V.

    
    </div>
    
    En la tabla siguiente se muestran las características disponibles (arriba) y las funciones que se ofrecen a los usuarios (izquierda). Las selecciones de la tabla son las opciones que debe seleccionar para habilitar dichas características para su organización.
    
    
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
    <th>Conferencia</th>
    <th>Conferencia de acceso telefónico local</th>
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
    <td><p>Conferencia</p></td>
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


5.  En la página **Seleccionar roles de servidor combinados** , puede combinar el servidor de mediación en el servidor front-end o para implementarlo como un servidor independiente.
    
    Puede combinar el servidor de mediación en el grupo de servidores front-end.
    
      - Si va a combinar el servidor de mediación en el grupo de servidores front-end Enterprise Edition, asegúrese de que la casilla está activada. Los roles de servidor se implementarán en los servidores del grupo.
    
      - Si tiene previsto implementar el servidor de mediación como un servidor independiente, desactive la casilla correspondiente. Implementará el servidor de mediación en un paso de implementación independiente después de implementar completamente el servidor front-end.
    
    <div>
    

    > [!NOTE]
    > Se recomienda combinar el servidor de mediación si fuera posible. Para obtener más información sobre la compatibilidad de los servidores de mediación combinados o independientes, consulte <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologs for Mediation Server in Lync Server 2013</A> en la documentación referente a la planeación.

    
    </div>

6.  La página **asociar roles de servidor con este grupo de servidores front-end** permite definir y asociar roles de servidor con el grupo de servidores front-end. Los tres roles disponibles son:
    
    **Habilitación de un grupo**     de servidores perimetrales Define y asocia un solo servidor perimetral o un grupo de servidores perimetrales. Un servidor perimetral facilita la comunicación y la colaboración entre usuarios dentro de la organización y personas fuera de la organización, incluidos los usuarios federados.
    
    Existen dos escenarios posibles que pueden usarse para implementar y asociar roles de servidor:
    
    Para el escenario uno, se define una nueva topología para una nueva instalación. Puede acometer la instalación de dos formas:
    
      - Dejar todas las casillas sin activar y proceder con la definición de la topología. Una vez que haya publicado, configurado y probado los roles de servidor front-end y back-end, puede volver a ejecutar el generador de topologías para agregar los servidores de roles a la topología. Esta estrategia le permitirá probar el grupo de servidores front-end y el servidor que ejecuta SQL Server sin complicaciones adicionales de roles adicionales. Una vez completadas las pruebas iniciales, puede volver a ejecutar el generador de topologías para seleccionar los roles que necesita implementar.
    
      - Seleccione los roles que necesita instalar y, a continuación, configure le hardware para hospedar los roles seleccionados.
    
    Para el escenario dos, tiene una implementación existente y la infraestructura está preparada para nuevos roles o debe asociar roles existentes con un nuevo servidor front-end:
    
      - En este caso, se seleccionan los roles que se van a implementar o asociar con el nuevo servidor front-end. En cualquier caso, continuará con la definición de los roles, la configuración de cualquier hardware necesario y procederá con la instalación.

7.  En la página **Definir el almacén de SQL**, realice una de las operaciones siguientes:
    
      - Para usar el almacén de SQL Server existente que ya se ha definido en la topología, seleccione **Usar un almacén de SQL definido previamente**.
    
      - Para definir una nueva instancia de SQL Server para almacenar la información del grupo de servidores, haga clic en **nuevo** y, a continuación, especifique el **FQDN de SQL Server**en el cuadro de diálogo **definir nuevo almacén de SQL** .
    
      - Para especificar el nombre de una instancia de SQL Server, seleccione **Instancia con nombre** y, a continuación, especifique el nombre de la instancia.
    
      - Para usar la instancia predeterminada, haga clic en **Instancia predeterminada**.
    
      - Para utilizar la creación de reflejos de SQL, seleccione **Habilitar creación de reflejos de SQL** y seleccione una instancia existente o cree una nueva instancia.

8.  En la página **Definir el uso compartido de archivos**, siga uno de estos procedimientos:
    
      - Para usar un uso compartido de archivos ya definido en la topología, seleccione **Usar un uso compartido de archivos ya definido**.
    
      - Para definir un nuevo recurso compartido de archivos, seleccione **Definir un nuevo recurso compartido de archivos**, en el cuadro **FQDN de servidor de archivos**, escriba el FQDN del servidor de archivos existente donde se ubicará el recurso compartido de archivos y, a continuación, escriba un nombre para el recurso compartido de archivos en el cuadro **Recurso compartido de archivos**.
    
    <div>
    

    > [!IMPORTANT]
    > El recurso compartido de archivos para Lync Server 2013 no se encuentra en el servidor front-end. Tenga en cuenta que, en este ejemplo, el recurso compartido de archivos se ha colocado en el servidor back-end basado en SQL Server. Esta podría no ser una ubicación óptima para los requisitos de su organización y es posible que un servidor de archivos fuera una opción mejor. Puede definir el uso compartido de archivos sin que este se haya creado. Tendrá que crear el uso compartido de archivos en la ubicación que defina antes de publicar la topología.

    
    </div>

9.  En la página **Especificar la dirección URL de servicios web**, siga uno o varios de estos procedimientos:
    
    <div>
    

    > [!IMPORTANT]
    > La dirección URL base es la identidad de servicios web de la dirección URL, menos https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net , la dirección URL base es pool01.contoso.net.

    
    </div>
    
    <div>
    

    > [!WARNING]
    > Si tiene más de un grupo front-end o servidor front-end, el FQDN de servicios web externos debe ser único. Por ejemplo, si define el FQDN de servicios web externos de un servidor front-end como <STRONG>pool01.contoso.com</STRONG>, no puede usar <STRONG>pool01.contoso.com</STRONG> para otro grupo de servidores front-end o servidor front-end.

    
    </div>
    
    1.  Si está configurando el equilibrio de carga de DNS, active la casilla **invalidar el FQDN del grupo de servicios Web interno** , escriba la dirección URL base interna (que debe ser diferente del FQDN del grupo de servidores y podría ser, por ejemplo, Internal- \<your base URL\> ) en la **dirección URL base interna**.
        
        <div>
        

        > [!WARNING]
        > Si decide reemplazar los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único en cualquier otro grupo de servidores front-end, director o grupo de directores. <STRONG>Use solo caracteres estándar</STRONG> (incluidos A – z, a – z, 0 – 9 y guiones) al definir direcciones URL o nombres de dominio completos. No use caracteres Unicode ni de subrayado. Los caracteres no estándar de una dirección URL o un FQDN no suelen ser compatibles con las CA públicas y DNS externas (es decir, cuando la dirección URL o el FQDN deben asignarse al nombre del sujeto o al nombre alternativo del sujeto del certificado).

        
        </div>
    
    2.  Opcionalmente, escriba la dirección URL base externa en **Dirección URL base externa**. Deberá introducir la dirección URL base externa con el fin de diferenciar la asignación de nombres de dominio interna. Por ejemplo, el dominio interno es contoso.net, pero el nombre del dominio externo es contoso.com. La dirección URL se define mediante el nombre de dominio contoso.com. También es importante en el caso de un proxy inverso. El nombre de dominio de la dirección URL base externa será el mismo que el nombre de dominio del FQDN del servidor proxy inverso. La mensajería instantánea y la presencia requieren acceso HTTP al grupo de servidores front-end.
    
    <div>
    

    > [!NOTE]
    > Para usar el equilibrio de carga de DNS, debe crear los registros DNS correspondientes. Para obtener más información, consulte <A href="lync-server-2013-configure-dns-for-load-balancing.md">configure DNS for Load Balancing in Lync Server 2013</A>.

    
    </div>

10. Si seleccionó **conferencias** en la **página seleccionar características** , en la página **seleccionar un servidor de Office Web Apps** , seleccione **asociar grupo con un servidor de Office Web Apps** y, a continuación, haga clic en **nuevo** (o seleccione un servidor de Office Web Apps existente en la lista desplegable).

11. En el cuadro de diálogo **Definir nuevo Office Web Apps Server**, escriba el nombre de dominio completo (FQDN) del equipo de Office Web Apps Server en el cuadro **FQDN de Office Web Apps Server**; al hacerlo, la dirección URL de descubrimiento de Office Web Apps Server deberá aparecer automáticamente en el cuadro **Dirección URL de descubrimiento de Office Web Apps Server**.
    
    Si Office Web Apps Server está instalado en local y en la misma zona de red que Lync Server 2013, la opción **Office Web Apps Server se implementa en una red externa (es decir, perimetral/Internet)** no debe seleccionarse.
    
    Si Office Web Apps Server está implementado fuera del firewall interno, seleccione la opción **Office Web Apps Server se implementa en una red externa (esto es, perimetral/Internet)**.
    
    <div>
    

    > [!NOTE]
    > Para obtener más información, consulte <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring Integration with Office Web Apps Server y Lync server 2013</A>.

    
    </div>

12. En la página **Definir el almacén de SQL para el archivado**, seleccione una instancia existente o un servidor SQL Server, o bien defina una nueva instancia para almacenar los datos asociados con los datos de archivado.

13. En la página **Definir el almacén SQL para la supervisión**, seleccione una instancia existente o un servidor SQL Server, o bien defina una nueva instancia para almacenar los datos asociados con los datos de supervisión.

14. Haga clic en **Siguiente**. Si ha definido otros servidores de roles en la página **asociar roles de servidor con este grupo de servidores front-end** , se abrirán las páginas del Asistente para configuración de roles independiente para que pueda configurar los roles de servidor. Para obtener más información, consulte lo siguiente:
    
    [Implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md)

15. Si no ha seleccionado roles de servidor adicionales para configurarlos e implementarlos, o una vez finalizada la configuración de los roles de servidor adicionales, haga clic en **Finalizar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

