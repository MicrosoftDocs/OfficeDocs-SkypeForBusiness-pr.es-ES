---
title: 'Lync Server 2013: cambiar la dirección URL de los servicios Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 934e448f48413df2938deab8a0d08389cfad37bd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a>Cambiar la dirección URL de los servicios web en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-11-16_

Al configurar las agrupaciones front-end y los servidores Standard Edition, tiene la opción de configurar un nombre de dominio completo (FQDN) y los puertos asociados de la granja de servidores web externos. Si no configuró esta dirección URL al ejecutar el Asistente para la implementación de Lync Server, tendrá que configurar manualmente esta configuración. Por lo general, un administrador no necesita modificar esta configuración, ya que son los puertos recomendados y predeterminados.

<div>


> [!NOTE]  
> La siguiente captura de pantalla se tomó al configurar un servidor Standard Edition, por lo que la opción reemplazar FQDN está deshabilitada. Esta opción está habilitada al configurar un servidor Enterprise Edition en un grupo de servidores front end.



</div>

![Editar la configuración del grupo de servicios Web](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Editar la configuración del grupo de servicios Web")

<div>

## <a name="to-configure-web-services"></a>Para configurar servicios Web

1.  Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.

2.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

3.  En el generador de topología, en el árbol de consola, en **servidores front-end Standard Edition**, **grupos de aplicaciones para el usuario de Enterprise Edition**y **grupos de directorios**, seleccione el nombre del grupo. Haga clic con el botón secundario en el nombre, haga clic en **Editar propiedades**y, a continuación, en **servicios web**.

4.  Agregue o edite el FQDN de los **servicios web externos**y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!WARNING]  
    > Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único. Por ejemplo, si define el FQDN de los servicios web externos de un servidor front-end como <STRONG>pool01.contoso.com</STRONG>, no puede usar <STRONG>pool01.contoso.com</STRONG> para otro grupo de servidores front-end o servidor front-end. Si también va a implementar directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro grupo de directores o directores, así como de cualquier grupo de servidores front-end o servidor front-end.

    
    </div>

5.  Verifique que los puertos de escucha y publicados estén configurados correctamente en su entorno.

6.  Repita estos pasos para todos los servidores Standard Edition, los grupos front-end y los grupos de directores de su entorno.

7.  En el árbol de consola, haga clic en **Lync Server 2013**y, a continuación, en el panel **acciones** , haga clic en **publicar topología**.

Hay algunos requisitos que debe tener en cuenta al configurar los puertos de escucha y publicación:

  - Los puertos de escucha que se muestran son los puertos que están configurados para Internet Information Server (IIS) en cada servidor front-end.

  - Los puertos de escucha internos y externos deben ser diferentes para IIS. En el caso de los puertos de escucha externos, estos suelen ser los mismos porque uno representa el equilibrador de carga de hardware para el tráfico web interno y otro representa el servidor proxy inverso para el tráfico web externo.

  - Puede invalidar los servicios Web internos en un grupo de servidores front-end, un director o un grupo de directores y definir su propio FQDN.
    
    <div>
    

    > [!WARNING]  
    > Si decide omitir los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único de cualquier otro grupo de servidores front-end, director o grupo de directores.

    
    </div>

  - Los puertos publicados deben estar configurados en el proxy inverso o en el equilibrador de carga de hardware como puertos en escucha.

  - Para un grupo de servidores front-end (no se muestra en el ejemplo), el FQDN del grupo interno de SIP debe ser diferente del FQDN de los servicios Web internos, porque el tráfico Web pasa por el equilibrador de carga de hardware y el tráfico de grupo interno de SIP se transmite a través del equilibrador de carga de DNS . Este requisito debe cumplirse.

  - Una implementación de Lync Server Standard Edition no necesita o permite que se invalide un FQDN de servicios Web internos porque no se puede equilibrar la carga de este servidor.

  - Si tiene un equilibrador de carga de hardware en su entorno que usa para tráfico interno y de SIP, el generador de topología no puede distinguirlo.
    
    Los FQDN de los servicios web deberían diferenciarse fácilmente entre sí; que ayuda a garantizar que el redireccionamiento URL dirija a los clientes hacia el servidor adecuado. Por ejemplo, si tiene dos FQDN, podría nombrar un meeting.contoso.com y el otro conferencing.contoso.com. Es posible que se produzcan problemas de redirección si tiene FQDN con nombres similares, como meet1.contoso.com y meet2.contoso.com.

Los servicios web externos funcionan conjuntamente con un proxy inverso en la red perimetral. Proporciona a los clientes acceso externo a usando estos servicios Web. Los FQDN que se configuran aquí se envían a los clientes cuando inician sesión y se usan para devolver una conexión HTTPS al proxy inverso cuando se conectan de forma remota. El servidor de proxy inverso reenvía el FQDN del servicio Web externo a un equilibrador de carga de hardware interno o directamente al grupo. El proxy inverso debe poder resolver el FQDN de los servicios web externos en la dirección IP del servidor Web interno. La FDQN de servicios web externos debe poder resolverse en la Internet pública.

Si su servidor interno es un servidor Standard Edition, el FQDN interno es el FQDN del servidor Standard Edition. Si el servidor interno es un grupo de servidores front-end, el FQDN es una IP virtual (VIP) de equilibrador de carga de hardware que equilibra la carga de los servidores internos de la granja de servidores Web. Es necesario un equilibrador de carga de hardware en un grupo de servidores front end con más de un servidor Enterprise Edition. Un equilibrador de carga no es necesario para un servidor Standard Edition o un servidor front-end Enterprise Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

