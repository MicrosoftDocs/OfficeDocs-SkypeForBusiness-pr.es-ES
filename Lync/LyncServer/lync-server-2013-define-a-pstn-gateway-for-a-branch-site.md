---
title: 'Lync Server 2013: Definir una puerta de enlace RTC para un sitio de sucursal'
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
ms.openlocfilehash: e4445647e6ffcbfc2cfc137bd120d0aced6a9908
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a>Definir una puerta de enlace RTC para un sitio de sucursal en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Realice este procedimiento en el sitio central, que contiene al menos un grupo de servidores front-end o un servidor Standard Edition.

<div>


> [!IMPORTANT]  
> Antes de llevar a cabo el procedimiento, deben cumplirse las condiciones siguientes: 
> <UL>
> <LI>
> <P>El software de&nbsp;comunicaciones de Lync Server 2013 debe estar configurado en el sitio central.</P>
> <LI>
> <P>El servidor de mediación debe implementarse en el sitio central.</P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a>Para definir una puerta de enlace RTC

1.  Haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En el árbol de consola, expanda el sitio central, expanda **sitios de sucursal**, expanda el nombre del sitio de la sucursal para el que desea definir una puerta de enlace de red telefónica conmutada (RTC) y, a continuación, expanda **componentes compartidos**.

3.  Haga clic con el botón secundario en **puertas de enlace RTC**y luego haga clic en **nueva puerta de enlace IP/PSTN**.

4.  En el cuadro de diálogo **definir nueva puerta de enlace IP/RTC** , haga clic en **FQDN o dirección IP**de la puerta de enlace y, a continuación, escriba el nombre de dominio completo (FQDN) o la dirección IP de la puerta de enlace que está implementando en el sitio de la sucursal.

5.  Haga clic en **Puerto de escucha para la puerta de enlace IP/RTC**y, a continuación, acepte los valores predeterminados.

6.  En la lista **Protocolo de transporte SIP** , haga clic en el protocolo de transporte que usa la puerta de enlace y, después, haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Por razones de seguridad, le recomendamos encarecidamente que use una puerta de enlace PSTN que admita la seguridad de la capa de transporte (TLS).

    
    </div>

<div>


> [!TIP]  
> Use el cmdlet <STRONG>set-CsPstnGateway</STRONG> para modificar las propiedades de una puerta de enlace RTC. Para obtener más información, vea <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">set-CsPstnGateway</A>en la ayuda del shell de administración de Lync Server.



</div>

**Paso siguiente** para la resistencia del sitio de sucursal: [configuración de usuarios para la resistencia de sitios de sucursal en Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

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

