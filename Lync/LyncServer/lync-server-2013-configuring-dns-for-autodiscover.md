---
title: 'Lync Server 2013: configuración de DNS para la detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cf81cd82655a37ad089d915e9e3799671025bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a>Configuración de DNS para la detección automática en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-12_

Para admitir la detección automática de los clientes de Lync, debe crear los siguientes registros del sistema de nombres de dominio (DNS):

  - Un registro DNS interno para admitir clientes de Lync que se conecten desde la red de la organización

  - Un registro DNS público o externo para admitir clientes de Lync que se conectan desde Internet

Debe crear un registro DNS interno y un registro DNS externo para cada dominio SIP.

Los registros DNS pueden ser A (host) o registros CNAME, en función de su capacidad para crear certificados nuevos con el nombre alternativo de asunto adicional (SAN). Si no puede solicitar e implementar un nuevo certificado externo (público) con el lyncdiscover. \<nombre\> de dominio San, use el procedimiento para usar el puerto http/TCP 80. Los procedimientos siguientes describen cómo crear registros DNS internos y externos.

<div>

## <a name="to-create-dns-cname-records"></a>Para crear registros CNAME de DNS

1.  Inicie sesión en un servidor DNS de la siguiente manera:
    
      - Para crear un registro DNS interno, inicie sesión en un servidor DNS de la red como miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.
    
      - Para crear un registro DNS externo, conéctese a su proveedor de DNS público.

2.  Abra el complemento administrativo DNS: haga clic en **Inicio**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **DNS**.

3.  Siga uno de estos pasos:
    
      - Para un registro DNS interno, en el árbol de consola del servidor DNS, expanda **zonas de búsqueda directa** para el dominio de Active Directory (por ejemplo, contoso. local).
        
        <div>
        

        > [!NOTE]  
        > Este dominio es el dominio de Active Directory donde se instalan&nbsp;el grupo de directores de Lync Server 2013 y el grupo de servidores front-end.

        
        </div>
    
      - Para un registro DNS externo, en el árbol de consola del servidor DNS, expanda **zonas de búsqueda directa** para su dominio SIP (por ejemplo, contoso.com).

4.  Compruebe que existe un registro para el grupo de directores de la siguiente manera:
    
      - Para un registro DNS interno, debe existir un registro A para el nombre de dominio completo (FQDN) de los servicios Web internos para el grupo de directores (por ejemplo, lyncwebdir01. contoso. local).
    
      - Para un registro DNS externo, debe existir un registro A host para el FQDN de los servicios web externos para el grupo de directores (por ejemplo, lyncwebextdir.contoso.com).

5.  Compruebe que existe un registro de host para el grupo de servidores front-end de la siguiente manera:
    
      - Para un registro DNS interno, debe existir un registro A en el FQDN de los servicios Web internos para el grupo de servidores front-end (por ejemplo, lyncwebpool01. contoso. local).
    
      - Para un registro DNS externo, debe existir un registro A host para el FQDN de los servicios web externos para el grupo de front-end (por ejemplo, lyncwebextpool01.contoso.com).

6.  Para un registro DNS interno, en el árbol de consola del servidor DNS, expanda **zonas de búsqueda directa** para su dominio SIP (por ejemplo, contoso.com).
    
    <div>
    

    > [!NOTE]  
    > Si va a crear un registro DNS externo, las <STRONG>zonas de búsqueda directa</STRONG> ya están expandidas para su dominio SIP del paso 3.

    
    </div>

7.  Haga clic con el botón derecho en el nombre de dominio SIP y después haga clic en **nuevo alias (CNAME)**.

8.  En **nombre de alias**, escriba una de las opciones siguientes:
    
      - Para un registro DNS interno, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio de detección automática.
    
      - Para un registro DNS externo, escriba lyncdiscover como nombre de host para la dirección URL del servicio de detección automática externa.

9.  En el **nombre de dominio completo (FQDN) del host de destino**, realice una de las siguientes acciones:
    
      - Para un registro DNS interno, escriba o busque el FQDN de servicios Web internos de su grupo de directores (por ejemplo, lyncwebdir01. contoso. local) y, a continuación, haga clic en **Aceptar**.
    
      - Para un registro DNS externo, escriba o busque el FQDN de servicios web externos para el grupo de directores (por ejemplo, lyncwebextdir.contoso.com) y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Si no usa un director, use el FQDN de los servicios Web internos y externos para el grupo de servidores front-end, o bien, para un único servidor, el FQDN del servidor front-end o el servidor Standard Edition.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Debe crear un nuevo registro CNAME de detección automática en la zona de búsqueda directa de cada dominio SIP que admita en el entorno de Lync Server 2013.

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a>Para crear registros A de DNS

1.  Inicie sesión en un servidor DNS de la siguiente manera:
    
      - Para crear un registro DNS interno, inicie sesión en un servidor DNS de la red como miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.
    
      - Para crear un registro DNS externo, conéctese a su proveedor de DNS público o servidor DNS externo.

2.  Abra el complemento administrativo DNS: haga clic en **Inicio**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **DNS**.

3.  Siga uno de estos pasos:
    
      - Para un registro DNS interno, en el árbol de consola del servidor DNS, expanda **zonas de búsqueda directa** para el dominio de Active Directory (por ejemplo, contoso. local).
        
        <div>
        

        > [!NOTE]  
        > Este dominio es el dominio de Active Directory donde se instalan&nbsp;el grupo de directores de Lync Server 2013 y el grupo de servidores front-end.

        
        </div>
    
      - Para un registro DNS externo, en el árbol de consola del servidor DNS, expanda **zonas de búsqueda directa** para su dominio SIP (por ejemplo, contoso.com).

4.  Compruebe que existe un registro A (para IPv6, AAAA) para el grupo de directores de la siguiente manera:
    
      - Para un registro DNS interno, debe existir un registro host A (para IPv6, AAAA) para el FQDN de los servicios Web internos para el grupo de directores (por ejemplo, lyncwebdir01. contoso. local).
    
      - Para un registro DNS externo, debe existir un registro host A (para IPv6, AAAA) para el FQDN de los servicios web externos para el grupo de directores (por ejemplo, lyncwebextdir.contoso.com).

5.  Compruebe que existe un registro host (para IPv6, AAAA) para el grupo de servidores front-end de la siguiente manera:
    
      - Para un registro DNS interno, debe existir un registro host A (para IPv6, AAAA) para el FQDN de los servicios Web internos de su grupo de front-end (por ejemplo, lyncwebpool01. contoso. local).
    
      - Para un registro DNS externo, debe existir un registro host (para IPv6, AAAA) para el FQDN de los servicios web externos para el grupo de front-end (por ejemplo, lyncwebextpool01.contoso.com).

6.  Para un registro DNS interno, en el árbol de consola del servidor DNS, expanda **zonas de búsqueda directa** para su dominio SIP (por ejemplo, contoso.com).
    
    <div>
    

    > [!NOTE]  
    > Si va a crear un registro DNS externo, las <STRONG>zonas de búsqueda directa</STRONG> ya están expandidas para su dominio SIP del paso 3.

    
    </div>

7.  Haga clic con el botón secundario en el nombre de dominio SIP y, a continuación, haga clic en **nuevo host (A o aaaa)**.

8.  En **nombre**, escriba el nombre de host como se indica a continuación:
    
      - Para un registro DNS interno, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio de detección automática.
    
      - Para un registro DNS externo, escriba lyncdiscover como nombre de host para la dirección URL del servicio de detección automática externa.
    
    <div>
    

    > [!NOTE]  
    > El nombre de dominio se supone de la zona en la que se define el registro y, por lo tanto, no es necesario escribirlo como parte del registro A.

    
    </div>

9.  En **dirección IP**, escriba la dirección IP de la siguiente manera:
    
      - Para un registro DNS interno, escriba la dirección IP de los servicios Web internos del Director (o bien, si usa un equilibrador de carga, escriba la dirección IP virtual (VIP) del equilibrador de carga del Director).
        
        <div>
        

        > [!NOTE]  
        > Si no usa un director, escriba la dirección IP del servidor front-end o del servidor Standard Edition, o bien, si usa un equilibrador de carga, escriba la VIP del equilibrador de carga del grupo de servidores front-end.

        
        </div>
    
      - Para un registro DNS externo, escriba la dirección IP externa o pública del proxy inverso.

10. Haga clic en **Agregar host**y, a continuación, en **Aceptar**.

11. Para crear un registro A adicional, repita los pasos 8 a 10.
    
    <div>
    

    > [!IMPORTANT]  
    > Debe crear una nueva lyncdiscover y lyncdiscoverinternal registros A en la zona de búsqueda directa de cada dominio SIP que admita en el entorno de Lync Server 2013.

    
    </div>

12. Cuando haya terminado de crear un registro (para IPv6, AAAA), haga clic en **listo**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

