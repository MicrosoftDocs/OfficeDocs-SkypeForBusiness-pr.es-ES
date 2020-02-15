---
title: 'Lync Server 2013: configurar adaptadores de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c114766bffb665e2c7da2850fefc6113365e4c2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a>Configurar adaptadores de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

Debe asignar una o más direcciones IP al adaptador de red externo y al menos una dirección IP al adaptador de red interno.

En los siguientes procedimientos, el servidor que ejecuta Forefront Threat Management Gateway (TMG) 2010 o el enrutamiento de solicitudes de aplicación de Internet Information Server tiene dos adaptadores de red:

  - Un adaptador de red público o externo para los clientes que intenten conectarse a su sitio web (es decir, normalmente a través de Internet).

  - Una interfaz de red privada, o interna, para los servidores internos que ejecutan Lync Server y que hospedan servicios Web.

<div>


> [!IMPORTANT]  
> De forma similar a los servidores perimetrales, solo se establece la puerta de enlace predeterminada en el adaptador de red externo. La puerta de enlace predeterminada será la dirección IP del enrutador o del firewall con conexión externa que dirige el tráfico a Internet. Para el tráfico destinado desde el proxy inverso al adaptador de red orientado interno, debe usar rutas estáticas persistentes (como el comando Route en Windows Server) para todas las subredes que contienen servidores a los que hacen referencia las reglas de publicación Web. Establecer una ruta persistente no hace que el equipo se convierta en un enrutador. Si el reenvío IP no está habilitado, el equipo solo actúa para dirigir tráfico específico destinado a otra red a la interfaz adecuada. Básicamente, esto configura dos puertas de enlace: una como la predeterminada que apunta a las redes externas y otra para el tráfico destinado a la interfaz interna y a un enrutador u otra red.<BR>Sin embargo, es posible que no sea necesario crear rutas persistentes para todas las subredes si los enrutadores de la red están configurados para resumir las rutas. Cree una ruta persistente a la red en la que se define el enrutador y use el enrutador como puerta de enlace predeterminada. Si no está seguro de cómo está configurada la red y necesita instrucciones sobre las rutas persistentes que deben crearse, consulte a los ingenieros de red de la empresa.<BR>El proxy inverso debe ser capaz de resolver los registros de host DNS (A) para el director interno o el servidor front-end y los FQDN de grupo de servidores de próximo salto usados en las reglas de publicación Web. Al igual que con los servidores perimetrales, por motivos de seguridad, le recomendamos que no configure un proxy inverso para que use un servidor DNS ubicado en la red interna. Esto significa que necesita servidores DNS en el perímetro o que necesita entradas de archivo de hosts en el proxy inverso que resuelve cada uno de estos FQDN a la dirección IP interna de los servidores.



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a>Para configurar las tarjetas adaptadoras de red en el equipo de proxy inverso

1.  En el servidor Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2 que se ejecuta como proxy inverso, Abra **Cambiar configuración del adaptador** haciendo clic en **Inicio**, seleccione **Panel de control**, haga clic en centro de **redes y recursos compartidos**y, a continuación, haga clic en **Cambiar configuración del adaptador**.

2.  Haga clic con el botón secundario en la conexión de red externa que desee usar para la interfaz externa y, a continuación, haga clic en **propiedades**.

3.  En la página de **propiedades** , haga clic en la ficha **red** , haga clic en **Protocolo de Internet versión 4 (TCP/IPv4)** en la lista **esta conexión utiliza los siguientes elementos** y, a continuación, haga clic en **propiedades**.

4.  En la página **propiedades del Protocolo de Internet (TCP/IP)** , configure las direcciones IP según corresponda para la subred de red a la que está conectado el adaptador de red.
    
    <div>
    

    > [!NOTE]  
    > Si el proxy inverso ya está siendo usado por otras aplicaciones que usan HTTPS/TCP/443, como para publicar Outlook Web Access, debe agregar otra dirección IP para que pueda publicar los servicios Web de Lync Server 2013 en HTTPS/TCP/443 sin interferir con las reglas y las escuchas de Web existentes, o bien debe reemplazar el certificado existente por uno que agregue los nuevos nombres completos externos al nombre alternativo de sujeto.

    
    </div>

5.  Haga clic en **Aceptar**y, a continuación, en **Aceptar**.

6.  En **conexiones de red**, haga clic con el botón secundario en la conexión de red interna que desea usar para la interfaz interna y, a continuación, haga clic en **propiedades**.

7.  Repita los pasos 3 a 5 para configurar la conexión de red interna.

</div>

</div>

<span> </span>

</div>

</div>

</div>

