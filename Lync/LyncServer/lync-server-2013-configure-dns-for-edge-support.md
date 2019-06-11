---
title: 'Lync Server 2013: Configurar DNS para admitir servidores perimetrales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79e1712b3425c7cce4020799b37f10aba894aeb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a>Configurar DNS para admitir servidores perimetrales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-15_

Debe configurar registros del sistema de nombres de dominio (DNS) para las interfaces de borde internos y externos, incluidas las interfaces de servidor perimetral y de proxy inverso. De forma predeterminada, los servidores perimetrales no se unen a un dominio y no tendrán un nombre de dominio completo (nombre de dominio completo). Solo se hace referencia al servidor perimetral por el nombre corto (equipo), no por un nombre de dominio completo. Sin embargo, Topology Builder usa FQDN, no nombres cortos. El nombre del servidor perimetral debe coincidir con el FQDN usado por el generador de topología. Para ello, define un sufijo DNS que, cuando se combina con el nombre del equipo, da como resultado el FQDN esperado. Use el procedimiento siguiente en "para agregar el sufijo DNS al nombre del equipo y el servidor perimetral que no está unido a un dominio" para agregar el sufijo DNS al nombre del equipo.

<div>


> [!NOTE]  
> De forma predeterminada, DNS usa un algoritmo de operación por turnos para girar el orden de los datos de registro de recursos devueltos en las respuestas de consulta cuando existan varios registros de recursos del mismo tipo para un nombre de dominio DNS consultado. El equilibrio de carga de DNS de Lync Server 2013, depende de la ronda por turnos de DNS como parte del mecanismo de equilibrio de carga de DNS. Compruebe que la configuración de operación por turnos no se ha deshabilitado. Si está usando un servidor DNS que no ejecuta un sistema operativo Windows, compruebe que la ordenación de los registros de recursos por turnos está habilitada.



</div>

Use los siguientes procedimientos en "**para crear un registro SRV de DNS**" para crear y comprobar cada registro SRV de DNS. Use el procedimiento de "**para crear un registro DNS**a" para definir los registros a de DNS necesarios para el acceso de usuarios externos. Para confirmar que los registros están configurados y funcionan correctamente, consulte "**para comprobar un registro DNS**" en este tema. Para obtener detalles sobre cada registro necesario para admitir el acceso de usuarios externos, consulte [determinar los requisitos de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a>Para agregar el sufijo DNS al nombre del equipo en un servidor perimetral que no está unido a un dominio

1.  En el equipo, haga clic en **Inicio**, haga clic con el botón secundario en **equipo**y, a continuación, haga clic en **propiedades**.

2.  En **configuración de nombre, dominio y grupo de trabajo del equipo**, haga clic en **Cambiar configuración**.

3.  En la pestaña **nombre de equipo** , haga clic en **cambiar**.

4.  En **cambios de nombre de equipo o dominio**, haga clic en **más**.

5.  En **sufijo DNS y nombre NetBIOS del equipo**, en **sufijo DNS principal de este equipo**, escriba el nombre del dominio interno (por ejemplo, Corp.contoso.com) y, a continuación, haga clic en **Aceptar** tres veces.

6.  Reinicie el equipo.

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a>Para crear un registro SRV de DNS

1.  En el servidor DNS adecuado, haga clic en **Inicio**, haga clic en **Panel de control**, haga clic en **herramientas administrativas**y, después, haga clic en **DNS**.
    
    <div>
    

    > [!IMPORTANT]  
    > Debe configurar DNS para que haya: 1) entradas DNS externas para búsquedas DNS externas de usuarios remotos y socios federados. 2) entradas para búsquedas DNS para su uso por parte de los servidores perimetrales dentro de la red perimetral (también se denomina DMZ, zona desmilitarizada y subred filtrada), incluidos los registros A de los servidores internos que ejecutan Lync Server 2013. y 3) entradas DNS internas para las búsquedas de los clientes internos y los servidores que ejecutan Lync Server 2013.

    
    </div>

2.  En el árbol de consola de su dominio SIP, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón secundario en el dominio donde está instalado Lync Server 2013.

3.  Haga clic en **otros registros nuevos**.

4.  En **seleccionar un tipo de registro de recursos**, escriba **Ubicación de servicio (SRV)** y, a continuación, haga clic en **crear registro**.

5.  Proporcione toda la información necesaria para el registro SRV de DNS.

</div>

<div>

## <a name="to-create-a-dns-a-record"></a>Para crear un registro A de DNS

1.  En el servidor DNS, haga clic en **Inicio**, haga clic en **Panel de control**, haga clic en **herramientas administrativas**y, después, haga clic en **DNS**.

2.  En el árbol de consola de su dominio SIP, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón secundario en el dominio en el que está instalado Lync Server 2013.

3.  Haga clic en **nuevo host (A)**.

4.  Proporcione toda la información necesaria para el registro SRV de DNS.

</div>

<div>

## <a name="to-verify-a-dns-record"></a>Para comprobar un registro DNS

1.  Inicie sesión en un equipo cliente del dominio.

2.  Haga clic en  **Inicio ** y en  **Ejecutar **.

3.  En el símbolo del sistema, ejecute el siguiente comando:
    
        nslookup <FQDN edge interface>

4.  Compruebe que recibe una respuesta que se resuelve en la dirección IP adecuada para el nombre de dominio completo (FQDN).

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear un registro DNS SRV para la integración con mensajería unificada (UM) hospedada de Exchange](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

