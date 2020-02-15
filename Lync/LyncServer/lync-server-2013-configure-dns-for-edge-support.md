---
title: 'Lync Server 2013: configurar DNS para compatibilidad con servidores perimetrales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e22228ec089f5632f30d4eabc2e8c32d87b5e2d5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a>Configurar DNS para admitir servidores perimetrales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-15_

Debe configurar registros DNS (Sistema de nombres de dominio) para las interfaces perimetrales interna y externa, incluidas las interfaces de proxy inverso y servidor perimetral. De modo predeterminado, los servidores perimetrales no se unen a un dominio y no dispondrán de un nombre de dominio completo (FQDN). Se menciona al servidor perimetral solo por el nombre corto (equipo), no por el nombre de dominio completo. Sin embargo, el generador de topologías usa FQDN, no nombres cortos. El nombre del servidor perimetral debe coincidir con el FQDN que usa el generador de topologías. Para ello, debe definir un sufijo DNS que, combinado con el nombre del equipo, resulte en el FQDN esperado. Utilice el procedimiento siguiente en "Añadir el sufijo DNS al nombre del equipo en un servidor perimetral que no se ha unido a un dominio" para añadir el sufijo DNS al nombre del equipo.

<div>


> [!NOTE]  
> De forma predeterminada, DNS usa un algoritmo Round Robin para girar el orden de los datos de registros de recursos devueltos en las respuestas a consultas donde existen varios registros de recursos del mismo tipo para un nombre de dominio DNS consultado. El equilibrio de carga de DNS de Lync Server 2013, depende de la Round-Robin de DNS como parte del mecanismo de equilibrio de carga de DNS. Compruebe que no se haya deshabilitado la configuración de operación por turnos. Si usa un servidor DNS que no ejecuta un sistema operativo Windows, compruebe que la ordenación de registros de recursos de Round-Robin está habilitada.



</div>

Utilice el procedimiento siguiente en “**Creación de un registro DNS SRV**” para crear y comprobar todos los registros SRV de DNS. Utilice el procedimiento en “**Creación de un registro A de DNS**” para definir los registros A de DNS necesarios para el acceso de usuarios externos. Para confirmar que los registros están configurados y funcionan correctamente, consulte “**Verificación de un registro DNS**” en este tema. Para obtener más información sobre cada registro necesario para admitir el acceso de usuarios externos, consulte [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a>Para agregar el sufijo DNS al nombre del equipo en un servidor perimetral que no se ha incorporado a un dominio

1.  En el equipo, haga clic en **Inicio**, haga clic con el botón secundario en **Equipo** y, a continuación, haga clic en **Propiedades**.

2.  En **Configuración del nombre del equipo, dominio y grupo de trabajo**, haga clic en **Cambiar configuración**.

3.  En la pestaña **Nombre del equipo**, haga clic en **Cambiar**.

4.  En **Cambios del nombre del equipo/dominio**, haga clic en **Más**.

5.  En **Sufijo DNS y nombre NetBIOS del equipo**, en **Sufijo DNS principal de este equipo**, escriba el nombre de su dominio interno (por ejemplo, corp.contoso.com), y haga clic en **Aceptar** tres veces.

6.  Reinicie el equipo.

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a>Para crear un registro SRV de DNS

1.  En el servidor DNS pertinente, haga clic en **Inicio**, en **Panel de control**, en **Herramientas administrativas** y, a continuación, en **DNS**.
    
    <div>
    

    > [!IMPORTANT]  
    > Debe configurar DNS para que haya: 1) entradas de DNS externas para las búsquedas DNS externas de usuarios remotos y socios federados; 2) entradas para búsquedas DNS que usan los servidores perimetrales dentro de la red perimetral (también denominada DMZ, zona desmilitarizada y subred filtrada), incluidos los registros A para los servidores internos que ejecutan Lync Server 2013; y 3) entradas DNS internas para búsquedas por parte de los clientes internos y los servidores que ejecutan Lync Server 2013.

    
    </div>

2.  En el árbol de la consola del dominio SIP, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón secundario en el dominio donde Lync Server 2013 está instalado.

3.  Haga clic en **Registros nuevos**.

4.  En **Seleccione el tipo de registro del recurso**, escriba **Ubicación de servicio (SRV)** y, a continuación, haga clic en **Crear registro**.

5.  Suministre toda la información necesaria para el registro SRV de DNS.

</div>

<div>

## <a name="to-create-a-dns-a-record"></a>Para crear un registro A de DNS

1.  En el servidor DNS, haga clic en **Inicio**, en **Panel de control**, en **Herramientas administrativas** y, a continuación, en **DNS**.

2.  En el árbol de la consola del dominio SIP, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón secundario en el dominio en el que Lync Server 2013 está instalado.

3.  Haga clic en **Host nuevo (A)**.

4.  Suministre toda la información necesaria para el registro SRV de DNS.

</div>

<div>

## <a name="to-verify-a-dns-record"></a>Para comprobar un registro DNS

1.  Inicie sesión en un equipo cliente en el dominio.

2.  Haga clic en **Inicio** y, a continuación, en **Ejecutar**.

3.  En el símbolo del sistema, ejecute el comando siguiente:
    
        nslookup <FQDN edge interface>

4.  Compruebe que recibe una respuesta que resuelve la dirección IP adecuada para el FQDN.

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear un registro SRV de DNS para la integración con la mensajería unificada de Exchange hospedada](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[Determinación de los requisitos de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

