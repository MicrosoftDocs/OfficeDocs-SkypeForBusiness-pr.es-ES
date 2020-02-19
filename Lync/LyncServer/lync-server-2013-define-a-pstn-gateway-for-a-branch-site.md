---
title: 'Lync Server 2013: definir una puerta de enlace RTC para un sitio de sucursal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d08e2010b79213607992ab383b606e7b609ca75e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a>Definir una puerta de enlace RTC para un sitio de sucursal en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Lleve a cabo este procedimiento en el sitio central, que contiene al menos un grupo de servidores front-end o un servidor Standard Edition.

<div>


> [!IMPORTANT]  
> Antes de llevar a cabo el procedimiento, se deben cumplir las siguientes condiciones: 
> <UL>
> <LI>
> <P>El software de&nbsp;comunicaciones de Lync Server 2013 debe estar configurado en el sitio central.</P>
> <LI>
> <P>El servidor de mediación debe implementarse en el sitio central.</P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a>Para definir una puerta de enlace RTC

1.  Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft Lync Server** y **Lync Server Topology Builder**.

2.  En el árbol de consola, expanda el sitio central, expanda **Sucursales**, expanda el nombre de la sucursal para la que desee definir una puerta de enlace de la red telefónica conmutada (RTC) y, a continuación, expanda **Componentes compartidos**.

3.  Haga clic con el botón secundario en **Puertas de enlace RTC** y, a continuación, en **Nueva puerta de enlace RTC/IP**.

4.  En el cuadro de diálogo **Definir la nueva puerta de enlace RTC/IP**, haga clic en **Dirección IP o FQDN de la puerta de enlace** y, a continuación, escriba el nombre de dominio completo (FQDN) o la dirección IP de la puerta de enlace que está implementando en la sucursal.

5.  Haga clic en **Puerto de escucha de la puerta de enlace RTC/IP** y acepte los valores predeterminados.

6.  En la lista **Protocolo de transporte SIP**, haga clic en el protocolo de transporte que usa la puerta de enlace y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Por motivos de seguridad, se recomienda encarecidamente usar una puerta de enlace RTC compatible con Seguridad de la capa de transporte (TLS).

    
    </div>

<div>


> [!TIP]  
> Use el cmdlet Set-<STRONG>Set-CsPstnGateway</STRONG> para modificar las propiedades de una puerta de enlace RTC. Para obtener más información, vea <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">set-CsPstnGateway</A>en la ayuda del shell de administración de Lync Server.



</div>

**Siguiente paso** para la resistencia de sitios de sucursal: [configuración de usuarios para la resistencia de sitios de sucursal en Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Opciones de implementación de la puerta de enlace RTC en Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

