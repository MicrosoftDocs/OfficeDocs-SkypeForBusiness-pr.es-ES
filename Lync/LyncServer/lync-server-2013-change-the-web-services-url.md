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
ms.openlocfilehash: 9eb2922913ee95bad11273b2e943812850da4402
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517824"
---
# <a name="change-the-web-services-url-in-lync-server-2013"></a>Cambiar la dirección URL de los servicios web en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-11-16_

Cuando configura los grupos de servidores front-end y los servidores Standard Edition, tiene la opción de configurar un nombre de dominio completo (FQDN) de la granja de servidores web externa y los puertos asociados. Si no configuró esta dirección URL cuando ejecutó el Asistente para la implementación de Lync Server, tendrá que configurar estas opciones de forma manual. Un administrador no suele necesitar modificar estos parámetros, ya que son los puertos predeterminados y recomendados.

<div>


> [!NOTE]  
> La siguiente captura de pantalla se realizó al configurar un servidor Standard Edition, por lo que la opción reemplazar FQDN está deshabilitada. Esta opción está habilitada al configurar un servidor Enterprise Edition en un grupo de servidores front-end.



</div>

![Edición de la configuración del grupo de servicios Web](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Edición de la configuración del grupo de servicios Web")

<div>

## <a name="to-configure-web-services"></a>Para configurar los servicios Web

1.  Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.

2.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

3.  En el generador de topologías, en el árbol de la consola, en **servidores front-end Standard Edition**, **grupos de servidores front-end Enterprise Edition**y **grupos de directorios**, seleccione el nombre del grupo. Haga clic con el botón secundario en el nombre, seleccione **Editar propiedades** y después haga clic en **Servicios web**.

4.  Agregue o edite el **FQDN de servicios web externos** y después haga clic en **Aceptar**.
    
    <div>
    

    > [!WARNING]  
    > Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único. Por ejemplo, si define el FQDN de servicios web externos de un servidor front-end como <STRONG>pool01.contoso.com</STRONG>, no puede usar <STRONG>pool01.contoso.com</STRONG> para otro grupo de servidores front-end o servidor front-end. Si también está implementando directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro director o grupo de directores, así como cualquier grupo de servidores front-end o servidor front-end.

    
    </div>

5.  Verifique que los puertos de escucha y los puertos publicados están configurados correctamente para su entorno.

6.  Repita estos pasos para todos los servidores Standard Edition, los grupos de servidores front-end y los grupos de servidores de Active Directory de su entorno.

7.  En el árbol de la consola, haga clic en **Lync Server 2013** y después en el panel **Acciones**, haga clic en **Publicar topología**.

A continuación se enumeran algunos requisitos que es necesario conocer a la hora de configurar los puertos de escucha y publicación.

  - Los puertos de escucha que se muestran son los puertos configurados para Internet Information Server (IIS) en cada servidor front-end.

  - Los puertos de escucha internos y externos deben ser diferentes para IIS. En el caso de los puertos de escucha externos, suele tratarse del mismo puerto, ya que uno representa el equilibrador de carga de hardware para el tráfico web interno y otro representa el servidor proxy inverso para el tráfico web externo.

  - Puede invalidar los servicios Web internos en un grupo de servidores front-end, en un director o en un grupo de directores y definir su propio FQDN.
    
    <div>
    

    > [!WARNING]  
    > Si decide reemplazar los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único en cualquier otro grupo de servidores front-end, director o grupo de directores.

    
    </div>

  - Los puertos publicados deben configurarse como puertos de escucha en el servidor proxy inverso o el equilibrador de carga de hardware.

  - En el caso de un grupo de servidores front-end (que no aparecen en el ejemplo), el FQDN del grupo de servidores SIP interno debe ser diferente al FQDN de servicios web internos, ya que el tráfico web viaja a través del equilibrador de carga de hardware, mientras que el tráfico del grupo de servidores SIP interno viaja a través el equilibrador de carga de DNS. Este requisito se debe cumplir.

  - Una implementación de Lync Server Standard Edition no necesita ni permitir que se invalide un FQDN de servicios Web interno porque no se puede equilibrar la carga de este servidor.

  - Si tiene un equilibrador de carga de hardware en su entorno que se usa para el tráfico SIP y Web interno, el generador de topologías no puede hacer la distinción.
    
    Los FQDN de servicio Web deben diferenciarse fácilmente entre sí; Esto ayuda a garantizar que los clientes apunten a los clientes hacia el servidor adecuado. Por ejemplo, si tiene dos FQDN, podría considerar la posibilidad de asignar un nombre a un meeting.contoso.com y el otro conferencing.contoso.com. Podría tener problemas de redirección si tiene FQDN con nombres más similares, como meet1.contoso.com y meet2.contoso.com.

Los servicios web externos trabajan en combinación con un proxy inverso en la red perimetral. Proporciona a los clientes acceso externo a con estos servicios Web. Los FQDN configurados aquí se envían a los clientes cuando inician sesión y se usan para hacer una conexión HTTPS con el proxy inverso en conexiones remotas. El servidor proxy inverso reenvía el FQDN de servicios web externo a un equilibrador de carga de hardware, o directamente al grupo de servidores. El proxy inverso debe poder resolver el FQDN de servicios web externos en la dirección IP del servidor web interno. El FDQN de servicios web externos debe poder resolverse en Internet.

Si el servidor interno es un servidor Standard Edition, el FQDN interno es el FQDN del servidor Standard Edition. Si el servidor interno es un grupo de servidores front-end, el FQDN es una IP virtual (VIP) de equilibrador de carga de hardware que equilibra la carga de la granja de servidores web internos. Es necesario un equilibrador de carga de hardware en un grupo de servidores front-end con varios servidores Enterprise Edition. No se requiere un equilibrador de carga para un servidor Standard Edition o un solo servidor front-end Enterprise Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

