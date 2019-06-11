---
title: 'Lync Server 2013: Crear y comprobar registros DNS SRV'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a539b58abbad323aaf7c7343b40eabb49d04d91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a>Crear y comprobar registros DNS SRV en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como miembro del grupo administradores de dominio o en miembro del grupo DnsAdmins.

En este tema se describe cómo configurar los registros del sistema de nombres de dominio (DNS) que se deben crear en implementaciones de Lync Server 2013 y los necesarios para iniciar sesión automáticamente en el cliente. Al crear un grupo de servidores front-end, el programa de instalación crea los objetos y la configuración de Active Directory para el grupo, incluido el nombre de dominio completo (FQDN) del grupo de servidores. Se crean objetos y configuraciones similares para un servidor Standard Edition. Para que los clientes puedan conectarse al servidor Standard Edition o del grupo, el FQDN del grupo o del servidor Standard Edition debe estar registrado en DNS. Debe crear registros SRV de DNS en el DNS interno para cada dominio SIP. En este procedimiento se supone que su DNS interno tiene zonas para sus dominios de usuario SIP.

<div>

## <a name="to-configure-a-dns-srv-record"></a>Para configurar un registro SRV de DNS

1.  En el servidor DNS, haga clic en **Inicio**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **DNS**.

2.  En el árbol de consola de su dominio SIP, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón secundario en el dominio SIP en el que se instalará Lync Server 2013.

3.  Haga clic en **otros registros nuevos**.

4.  En **Seleccione el tipo de registro del recurso**, haga clic en **Ubicación de servicio (SRV)** y, luego, haga clic en **Crear registro**.

5.  Haga clic en **servicio**y, a continuación, escriba ** \_sipinternaltls**.

6.  Haga clic en **Protocolo**y, a continuación, escriba ** \_TCP**.

7.  Haga clic en **Número de puerto** y, luego, escriba **5061**.

8.  Haga clic en **Host que ofrece este servicio** y, luego, escriba el FQDN del grupo de servidores o del servidor Standard Edition.

9.  Haga clic en **Aceptar** y, luego, haga clic en **Listo**.

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a>Para comprobar la creación de un registro SRV de DNS

1.  Inicie sesión en un equipo cliente del dominio con una cuenta que sea miembro del grupo Usuarios autenticados o que tenga permisos equivalentes.

2.  Haga clic en  **Inicio ** y en  **Ejecutar **.

3.  En el cuadro **abrir** , escriba **cmd**y haga clic en **Aceptar**.

4.  En el símbolo del sistema, escriba **nslookup**y, a continuación, presione Entrar.

5.  Escriba **set Type = SRV**y, a continuación, presione Entrar.

6.  Escriba ** \_sipinternaltls.\_ tcp.contoso.com**y, a continuación, presione Entrar. La salida mostrada para el registro de seguridad de la capa de transporte (TLS) es la siguiente:
    
    Servidor: \<DNS server\>. contoso.com
    
    Address: \<dirección IP del servidor DNS\>
    
    Respuesta no autoritaria:
    
    \_sipinternaltls. \_Ubicación del servicio TCP.contoso.com SRV:
    
    prioridad = 0
    
    peso = 0
    
    puerto = 5061
    
    SVR hostname = poolname.contoso.com (o un registro de servidor Standard Edition A)
    
    poolname.contoso.com internet address = \<dirección IP virtual del equilibrador de carga\> o \<la dirección IP de un servidor Enterprise Edition único para grupos con un solo servidor\> Enterprise Edition \<o una dirección IP del estándar Servidor de edición\>

7.  Cuando haya terminado, en el símbolo del sistema, escriba **Exit**y, a continuación, presione Entrar.

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Para comprobar que se puede resolver el FQDN del grupo de servidores front-end o del servidor Standard Edition

1.  Inicie sesión en un equipo cliente del dominio.

2.  Haga clic en  **Inicio ** y en  **Ejecutar **.

3.  En el cuadro **abrir** , escriba **cmd**y haga clic en **Aceptar**.

4.  En el símbolo del sistema, escriba **nslookup** \<FQDN del grupo\> de servidores Front \<-end o FQDN del servidor\>Standard Edition y, a continuación, presione Entrar.

5.  Compruebe que recibe una respuesta que se resuelve en la dirección IP adecuada para el nombre de dominio completo (FQDN).

</div>

</div>

<span> </span>

</div>

</div>

</div>

