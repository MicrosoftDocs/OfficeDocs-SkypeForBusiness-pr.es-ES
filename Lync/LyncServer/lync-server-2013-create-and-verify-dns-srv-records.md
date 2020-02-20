---
title: 'Lync Server 2013: crear y comprobar registros DNS SRV'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 677b657f5bb7dacad6f1379aa4923052ba4ab1c5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a>Crear y comprobar registros DNS SRV en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o dominio, al menos, como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.

En este tema se describe cómo configurar los registros del sistema de nombres de dominio (DNS) que se deben crear en las implementaciones de Lync Server 2013 y los que se requieren para el inicio de sesión automático de los clientes. Cuando se crea un grupo de servidores front-end, el programa de instalación crea los objetos y la configuración de Active Directory para el grupo, incluido el nombre de dominio completo (FQDN) del grupo de servidores. Se crean objetos y configuraciones similares para un servidor Standard Edition. Para que los clientes puedan conectar con el servidor Standard Edition o el grupo de servidores, el FQDN del grupo de servidores o del servidor Standard Edition debe estar registrado en DNS. Debe crear registros DNS SRV en su DNS interno para cada dominio SIP. En este procedimiento, se presupone que el DNS interno tiene zonas para los dominios de usuarios SIP.

<div>

## <a name="to-configure-a-dns-srv-record"></a>Para configurar un registro DNS SRV

1.  En el servidor DNS, haga clic en **Inicio**, **Herramientas administrativas** y, a continuación, **DNS**.

2.  En el árbol de la consola del dominio SIP, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón secundario en el dominio SIP en el que se instalará Lync Server 2013.

3.  Haga clic en **Registros nuevos**.

4.  En **Seleccione el tipo de registro del recurso**, haga clic en **Ubicación de servicio (SRV)** y, a continuación, haga clic en **Crear registro**.

5.  Haga clic en **servicio**y, a continuación, escriba ** \_sipinternaltls**.

6.  Haga clic en **Protocolo**y, a continuación, escriba ** \_TCP**.

7.  Haga clic en **Número de puerto** y escriba **5061**.

8.  Haga clic en **host que ofrece este servicio**y, a continuación, escriba el FQDN del grupo de servidores o del servidor Standard Edition.

9.  Haga clic en **Aceptar** y, a continuación, haga clic en **Listo**.

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a>Para comprobar la creación de un registro DNS SRV

1.  Inicie sesión en un equipo cliente del dominio con una cuenta que sea miembro del grupo Usuarios autenticados o que tenga permisos equivalentes.

2.  Haga clic en **Inicio** y, a continuación, en **Ejecutar**.

3.  En el cuadro **Abrir**, escriba **cmd** y, a continuación, haga clic en **Aceptar**.

4.  En el símbolo del sistema, escriba **nslookup** y, a continuación, presione ENTRAR.

5.  Escriba **set type=srv** y, a continuación, presione ENTRAR.

6.  Escriba ** \_sipinternaltls.\_ tcp.contoso.com**y, a continuación, presione Entrar. El resultado que se muestra para el registro de Seguridad de la capa de transporte (TLS) es el siguiente:
    
    Servidor: \<servidor\>DNS. contoso.com
    
    Dirección: \<dirección IP del servidor DNS\>
    
    Respuesta no autoritativa:
    
    \_sipinternaltls. \_Ubicación del servicio SRV de TCP.contoso.com:
    
    prioridad = 0
    
    Weight = 0
    
    Port = 5061
    
    SVR hostname = poolname.contoso.com (o registro A de servidor Standard Edition)
    
    poolname.contoso.com internet address = \<dirección IP virtual del equilibrador de carga\> o \<dirección IP de un servidor Enterprise Edition único para grupos con un solo servidor\> Enterprise Edition o \<dirección IP del servidor Standard Edition\>

7.  Cuando termine, en el símbolo del sistema, escriba **exit** y, a continuación, presione ENTRAR.

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Para comprobar que se puede resolver el FQDN del grupo de servidores front-end o del servidor Standard Edition

1.  Inicie sesión en un equipo cliente en el dominio.

2.  Haga clic en **Iniciar** y, a continuación, en **Ejecutar**.

3.  En el cuadro **Abrir**, escriba **cmd** y, a continuación, haga clic en **Aceptar**.

4.  En el símbolo del sistema, escriba **nslookup** \<FQDN del grupo\> de servidores Front \<-end o el FQDN del\>servidor Standard Edition y, a continuación, presione Entrar.

5.  Compruebe que recibe una respuesta que resuelve la dirección IP adecuada para el FQDN.

</div>

</div>

<span> </span>

</div>

</div>

</div>

