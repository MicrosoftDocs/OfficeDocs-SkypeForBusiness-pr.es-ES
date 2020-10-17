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
ms.openlocfilehash: 249993e68930db1eb5dd5159633a73f80cef8c05
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520057"
---
# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a>Configuración de DNS para la detección automática en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-12_

Para admitir la detección automática de clientes de Lync, debe crear los siguientes registros del sistema de nombres de dominio (DNS):

  - Un registro DNS interno para admitir clientes de Lync que se conectan desde dentro de la red de la organización

  - Un registro DNS externo, o público, para admitir clientes de Lync que se conectan desde Internet

Debe crear un registro DNS interno y un registro DNS externo para cada dominio SIP.

Los registros DNS pueden ser registros CNAME o registros A (host), en función de la capacidad de crear nuevos certificados con el nombre alternativo de sujeto adicional (SAN). Si no puede solicitar e implementar un nuevo certificado externo (público) con el lyncdiscover.\<domain name\> SAN, use el procedimiento para usar el puerto HTTP/TCP 80. Los siguientes procedimientos describen cómo crear registros DNS internos y externos.

<div>

## <a name="to-create-dns-cname-records"></a>Para crear registros CNAME de DNS

1.  Inicie sesión en un servidor DNS de la siguiente manera:
    
      - Para crear un registro DNS interno, inicie sesión en un servidor DNS de su red como miembro del grupo Domain Admins o miembro del grupo DnsAdmins.
    
      - Para crear un registro DNS externo, conéctese a su proveedor de DNS público.

2.  Abra el complemento administrativo de DNS: haga clic en **Iniciar**, en **Herramientas administrativas** y en **DNS**.

3.  Siga uno de estos procedimientos:
    
      - Para un registro DNS interno, en el árbol de la consola del servidor DNS, expanda **Zonas de búsqueda directa** para su domino de Active Directory (por ejemplo, contoso.local).
        
        <div>
        

        > [!NOTE]  
        > Este dominio es el dominio de Active Directory en el que &nbsp; se instalan el grupo de directores de Lync Server 2013 y el grupo de servidores front-end.

        
        </div>
    
      - Para un registro DNS externo, en el árbol de la consola del servidor DNS, expanda  **Zonas de búsqueda directa**para su dominio SIP (por ejemplo, contoso.com).

4.  Compruebe que existe un registro de host A para su grupo de directores de la siguiente manera:
    
      - Para un registro DNS interno, debe haber un registro de host A para el nombre de dominio completo (FQDN) de servicios Web internos del grupo de directores (por ejemplo, lyncwebdir01. contoso. local).
    
      - Para un registro DNS externo, debe haber un registro de host A para el FQDN de servicios web externos para el grupo de directores (por ejemplo, lyncwebextdir.contoso.com).

5.  Compruebe que existe un registro de host A para el grupo de servidores front-end de la siguiente manera:
    
      - Para un registro DNS interno, debe haber un registro de host A para el FQDN de servicios Web internos del grupo de servidores front-end (por ejemplo, lyncwebpool01. contoso. local).
    
      - Para un registro DNS externo, debe haber un registro de host A para el FQDN de servicios web externos del grupo de servidores front-end (por ejemplo, lyncwebextpool01.contoso.com).

6.  Para un registro DNS interno, en el árbol de la consola del servidor DNS, expanda **Zonas de búsqueda directa** para su domino SIP (por ejemplo, contoso.com).
    
    <div>
    

    > [!NOTE]  
    > Si crea un registro DNS externo, <STRONG>Zonas de búsqueda directa</STRONG> ya está expandido en su domino SIP desde el paso 3.

    
    </div>

7.  Haga clic con el botón secundario del mouse en el nombre de dominio SIP y, a continuación, haga clic en **Nuevo alias (CNAME)**.

8.  En **Nombre de alias**, escriba una de las siguientes opciones:
    
      - Para un registro DNS interno, escriba lyncdiscoverinternal como nombre de host para la dirección URL del servicio Detección automática interna.
    
      - Para un registro DNS externo, escriba lyncdiscover como nombre de host para la dirección URL del servicio Detección automática externa.

9.  En **Nombre de dominio completo (FQDN) para el host de destino**, realice una de las operaciones siguientes:
    
      - Para un registro DNS interno, escriba o busque el FQDN de servicios Web interno de su grupo de directores (por ejemplo, lyncwebdir01. contoso. local) y, a continuación, haga clic en **Aceptar**.
    
      - Para un registro DNS externo, escriba o busque el FQDN de servicios web externos para el grupo de directores (por ejemplo, lyncwebextdir.contoso.com) y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Si no usa un director, use el FQDN de servicios Web internos y externos para el grupo de servidores front-end, o bien, para un solo servidor, el FQDN para el servidor front-end o el servidor Standard Edition.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Debe crear un nuevo registro CNAME de detección automática en la zona de búsqueda directa de cada dominio SIP que admita en su entorno de Lync Server 2013.

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a>Para crear registros DNS A

1.  Inicie sesión en un servidor DNS de la siguiente manera:
    
      - Para crear un registro DNS interno, inicie sesión en un servidor DNS de su red como miembro del grupo Domain Admins o miembro del grupo DnsAdmins.
    
      - Para crear un registro DNS externo, conéctese a su proveedor de DNS público o al servidor DNS externo.

2.  Abra el complemento administrativo de DNS: haga clic en **Iniciar**, en **Herramientas administrativas** y en **DNS**.

3.  Siga uno de estos procedimientos:
    
      - Para un registro DNS interno, en el árbol de la consola del servidor DNS, expanda **Zonas de búsqueda directa** para su domino de Active Directory (por ejemplo, contoso.local).
        
        <div>
        

        > [!NOTE]  
        > Este dominio es el dominio de Active Directory en el que &nbsp; se instalan el grupo de directores de Lync Server 2013 y el grupo de servidores front-end.

        
        </div>
    
      - Para un registro DNS externo, en el árbol de la consola del servidor DNS, expanda  **Zonas de búsqueda directa**para su dominio SIP (por ejemplo, contoso.com).

4.  Compruebe que exista un registro de host A (para IPv6, AAAA) para el grupo de directores de la siguiente manera:
    
      - Para un registro DNS interno, debe haber un registro de host A (para IPv6, AAAA) para el FQDN de servicios Web internos del grupo de directores (por ejemplo, lyncwebdir01. contoso. local).
    
      - Para un registro DNS externo, debe haber un registro de host A (para IPv6, AAAA) para el FQDN de servicios web externos del grupo de directores (por ejemplo, lyncwebextdir.contoso.com).

5.  Compruebe que existe un registro de host A (para IPv6, AAAA) para el grupo de servidores front-end de la siguiente manera:
    
      - Para un registro DNS interno, debe haber un registro de host A (para IPv6, AAAA) para el FQDN de servicios Web internos del grupo de servidores front-end (por ejemplo, lyncwebpool01. contoso. local).
    
      - Para un registro DNS externo, debe haber un registro de host A (para IPv6, AAAA) para el FQDN de servicios web externos del grupo de servidores front-end (por ejemplo, lyncwebextpool01.contoso.com).

6.  Para un registro DNS interno, en el árbol de la consola del servidor DNS, expanda **Zonas de búsqueda directa** para su domino SIP (por ejemplo, contoso.com).
    
    <div>
    

    > [!NOTE]  
    > Si crea un registro DNS externo, <STRONG>Zonas de búsqueda directa</STRONG>ya está expandido en su domino SIP desde el paso 3.

    
    </div>

7.  Haga clic con el botón secundario del mouse en el nombre de dominio SIP y, a continuación, haga clic en **Nuevo host (A o AAAA)**.

8.  En **Nombre**, escriba el nombre de host de la siguiente manera:
    
      - Para un registro DNS interno, escriba lyncdiscoverinternal como nombre de host para la dirección URL del servicio Detección automática interna.
    
      - Para un registro DNS externo, escriba lyncdiscover como nombre de host para la dirección URL del servicio Detección automática externa.
    
    <div>
    

    > [!NOTE]  
    > El nombre de dominio se deduce de la zona en la que se define el registro y, por lo tanto, no es necesario introducirlo como parte del registro A.

    
    </div>

9.  En **Dirección IP**, escriba la dirección IP de la siguiente manera:
    
      - Para un registro DNS interno, escriba la dirección IP de los servicios Web internos del Director (o bien, si usa un equilibrador de carga, escriba la IP virtual (VIP) del equilibrador de carga del Director).
        
        <div>
        

        > [!NOTE]  
        > Si no usa un director, escriba la dirección IP del servidor front-end o del servidor Standard Edition, o bien, si usa un equilibrador de carga, escriba la VIP del equilibrador de carga del grupo de servidores front-end.

        
        </div>
    
      - Para un registro DNS externo, escriba la dirección IP externa o pública del proxy inverso.

10. Haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**.

11. Para crear un registro A adicional, repita los pasos del 8 al 10.
    
    <div>
    

    > [!IMPORTANT]  
    > Debe crear un nuevo lyncdiscover y lyncdiscoverinternal A registros A en la zona de búsqueda directa de cada dominio SIP que admita en su entorno de Lync Server 2013.

    
    </div>

12. Cuando acabe de crear registros A (para IPv6, AAAA), haga clic en **Listo**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

