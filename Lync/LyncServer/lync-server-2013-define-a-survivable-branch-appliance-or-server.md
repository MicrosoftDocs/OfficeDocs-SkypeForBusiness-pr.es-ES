---
title: 'Lync Server 2013: Definir un servidor o aplicación de sucursal con funciones de supervivencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dadaa26f6a951995906ed29ffd0615da16066928
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Definir un servidor o aplicación de sucursal con funciones de supervivencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-07_

Lleve a cabo este procedimiento en el sitio central si no definió el equipo o servidor de rama que funciona bien cuando lo agregó a su topología.

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a>Para definir un equipo de sucursal o un servidor de sucursal con la supervivencia

1.  Haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En el árbol de consola, expanda el sitio central, expanda **sitios de sucursal**y, a continuación, expanda el nombre del sitio de la sucursal donde planea implementar el equipo con la sucursal o el servidor de sucursal que pueda superviviente.

3.  Haga clic con el botón derecho en **dispositivos de sucursales**supervivientes y, a continuación, haga clic en **nuevo dispositivo de sucursal**.
    
    <div>
    

    > [!IMPORTANT]  
    > Los equipos de las <STRONG>sucursales</STRONG> con las que son supervivientes son los que definen servidores de sucursal y las aplicaciones de la que son supervivientes.

    
    </div>

4.  En el cuadro de diálogo **definir aplicación de aplicación** reinstalable, haga clic en **FQDN**, escriba el nombre de dominio completo (FQDN) de la aplicación de la rama que funcionará con la supervivencia o el servidor de sucursal con la supervivencia que va a implementar en este sitio de la sucursal y haga clic en **siguiente**.
    
    <div>
    

    > [!IMPORTANT]  
    > Si está definiendo una aplicación de un equipo que pueda ser superviviente, el nombre que escriba en <STRONG>FQDN</STRONG> debe ser el mismo que el FQDN de la aplicación de rama superviviente que asignó al atributo <STRONG>ServicePrincipalName</STRONG> . Para obtener más información, vea <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Agregar una aplicación de rama que se puede hacer a Active Directory en Lync Server 2013</A>.

    
    </div>

5.  Haga clic en **grupo de servidores front-end**, haga clic en el servidor front-end (grupo de servicios de usuario) en el sitio central al que se conectará este equipo con la sucursal o el servidor de sucursal supervivientes y, a continuación, haga clic en **siguiente**.

6.  Haga clic en **servidor perimetral**, haga clic en el grupo perimetral al que se conectará esta aplicación de sucursal o servidor de sucursal supervivientes para proporcionar conectividad RTC a los usuarios remotos del sitio de la sucursal y, a continuación, haga clic en **siguiente**.

7.  Haga clic en **FQDN de la puerta de enlace o dirección IP**y, a continuación, escriba el FQDN o la dirección IP de la puerta de enlace del mismo nivel a la que la sucursal o el servidor de sucursal superviviente está asociado para enrutar llamadas RTC entrantes o salientes.
    
    <div>
    

    > [!IMPORTANT]  
    > Si está definiendo un dispositivo de sucursal que funciona bien, esta es la puerta de enlace a la que se conectará el servidor de mediación de la aplicación de la sucursal con la que se puede obtener conectividad RTC.

    
    </div>

8.  Haga clic en **Puerto de escucha para la puerta de enlace IP/RTC**y, a continuación, acepte el puerto predeterminado.

9.  En **Protocolo de transporte SIP**, haga clic en el protocolo de transporte que usará el equipo de la sucursal o el servidor de sucursal supervivientes y, a continuación, haga clic en **Finalizar**.
    
    <div>
    

    > [!NOTE]  
    > Por razones de seguridad, le recomendamos encarecidamente que use la seguridad de la capa de transporte (TLS). Si está definiendo un dispositivo de sucursal que es reviviente, consulte la documentación del proveedor de su equipo de sucursales que sea superviviente para verificar que su equipo de sucursales con la supervivencia es compatible con el protocolo TLS.

    
    </div>

10. En el árbol de consola, haga clic con el botón derecho en el nuevo dispositivo de sucursal o servidor que sea reviviente, haga clic en **topología**y luego en **publicar**.

**Siguiente paso**: [implementar un equipo o servidor de rama con la supervivencia con Lync Server 2013: tarea de sitio de sucursal](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

