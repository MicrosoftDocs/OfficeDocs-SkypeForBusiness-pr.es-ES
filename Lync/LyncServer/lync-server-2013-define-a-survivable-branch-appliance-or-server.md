---
title: 'Lync Server 2013: definir una aplicación o un servidor de sucursal con funciones de supervivencia'
description: 'Lync Server 2013: definir una aplicación o un servidor de sucursal con funciones de supervivencia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 946aec82f33dffe268fefb3548b8db2f5c19e1a8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567766"
---
# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Definir una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-07_

Lleve a cabo este procedimiento en el sitio central en caso de que no haya definido la aplicación o el servidor de sucursal con funciones de supervivencia tras agregarlos a la topología.

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a>Para definir una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia

1.  Haga clic en **Inicio**, en **todos los programas**, en **Microsoft Lync Server 2013**y, a continuación, en **generador de topologías de Lync Server**.

2.  En el árbol de la consola, expanda el sitio central, expanda **sitios de sucursal**y, a continuación, expanda el nombre del sitio de sucursal en el que va a implementar la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia.

3.  Haga clic con el botón secundario en **aplicaciones de sucursal**con funciones de supervivencia y haga clic en **nueva aplicación de sucursal**con funciones de supervivencia.
    
    <div>
    

    > [!IMPORTANT]  
    > Las <STRONG>aplicaciones de sucursal</STRONG> con funciones de supervivencia son donde define servidores de sucursal con funciones de supervivencia y aplicaciones de sucursal con funciones de supervivencia.

    
    </div>

4.  En el cuadro de diálogo **definir aplicación de sucursal** con funciones de supervivencia, haga clic en **FQDN**, escriba el nombre de dominio completo (FQDN) de la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia que se implementará en este sitio de sucursal y, a continuación, haga clic en **siguiente**.
    
    <div>
    

    > [!IMPORTANT]  
    > Si está definiendo una aplicación de sucursal con funciones de supervivencia, el nombre que escriba en el <STRONG>FQDN</STRONG> debe ser el mismo que el FQDN de aplicación de sucursal con funciones de supervivencia asignado al atributo <STRONG>ServicePrincipalName</STRONG> . Para obtener más información, consulte <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory en Lync Server 2013</A>.

    
    </div>

5.  Haga clic en **grupo de servidores front-end**, haga clic en el servidor front-end (grupo de servicios de usuario) en el sitio central al que se conectará esta aplicación de sucursal con funciones de supervivencia o con un servidor de sucursal con funciones de supervivencia y haga clic en **siguiente**.

6.  Haga clic en **servidor perimetral**, haga clic en el grupo de servidores perimetrales al que se conectará esta aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia para proporcionar conectividad RTC a usuarios remotos del sitio de sucursal y, a continuación, haga clic en **siguiente**

7.  Haga clic en **dirección IP o FQDN de puerta de enlace**y, a continuación, escriba el FQDN o la dirección IP de la puerta de enlace del mismo nivel a la que la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia tienen asociado el enrutamiento de llamadas RTC de entrada o de salida.
    
    <div>
    

    > [!IMPORTANT]  
    > Si está definiendo una aplicación de sucursal con funciones de supervivencia, esta es la puerta de enlace a la que se conectará el servidor de mediación de dicha aplicación para conectividad de red telefónica conmutada (RTC).

    
    </div>

8.  Haga clic en **Puerto de escucha para puerta de enlace IP/RTC** y acepte el puerto predeterminado.

9.  En **Protocolo de transporte SIP**, haga clic en el protocolo de transporte que usará la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia y, a continuación, haga clic en **Finalizar**.
    
    <div>
    

    > [!NOTE]  
    > Por motivos de seguridad, se recomienda encarecidamente usar Seguridad de la capa de transporte (TLS). Si está definiendo una aplicación de sucursal con funciones de supervivencia, consulte la documentación del proveedor para verificar que dicha aplicación admita el protocolo de Seguridad de la capa de transporte (TLS).

    
    </div>

10. En el árbol de la consola, haga clic con el botón secundario en la nueva aplicación o servidor de sucursal con funciones de supervivencia, haga clic en **Topología** y después haga clic en **Publicar**.

**Siguiente paso**: [implementar una aplicación o un servidor de sucursal con funciones de supervivencia con Lync Server 2013: tarea de sitio de sucursal](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

