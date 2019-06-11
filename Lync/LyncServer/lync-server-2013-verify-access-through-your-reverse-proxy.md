---
title: 'Lync Server 2013: Comprobar el acceso a través del proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e35e3908f66952b0e631484efa590bcd76fc0456
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a>Comprobar el acceso a través del proxy inverso en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-29_

Use el procedimiento siguiente para comprobar que los usuarios pueden obtener acceso a la información del proxy inverso. Es posible que tenga que completar la configuración del firewall y del sistema de nombres de dominio (DNS) antes de que Access funcione correctamente.

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a>Para comprobar que puede obtener acceso al sitio web a través de Internet

  - Abra un explorador Web, escriba las direcciones URL en la barra de **direcciones** que los clientes usan para acceder a los archivos de la libreta de direcciones y el sitio web para las conferencias de la siguiente manera:
    
      - En servidor de la libreta de direcciones, escriba una dirección URL similar **https://externalwebfarmFQDN/abs** a la siguiente: donde externalwebfarmFQDN es el FQDN externo de los servicios web externos que hospedan los servicios de libreta de direcciones. El usuario debe recibir un desafío HTTP, ya que la seguridad de directorios de la carpeta del servidor de la libreta de direcciones está configurada de forma predeterminada en la autenticación de Windows.
    
      - Para conferencias, escriba una dirección URL similar a la siguiente **https://externalwebfarmFQDN/meet** : donde externalwebfarmFQDN es el FQDN externo de la granja de servidores web que hospeda el contenido de la reunión. Esta dirección URL debe mostrar la página de solución de problemas para conferencias. También puede confirmar que su dirección URL simple para conferencias funciona correctamente. Una dirección URL sencilla de ejemplo para la combinación de conferencia puede serhttps://meet.contoso.com
    
      - En expansión de grupos de distribución, escriba una dirección URL similar a **https://externalwebfarmFQDN/GroupExpansion/service.svc**la siguiente:. El usuario debe recibir un desafío HTTP, porque la seguridad de directorio en el servicio de expansión del grupo de distribución está configurada de forma predeterminada en la autenticación de Windows.
    
      - Para el acceso telefónico, escriba la dirección URL sencilla similar a la **https://externalwebfarmFQDN/dialin** siguiente, donde externalwebfarmFQDN es el nombre completo externo del conjunto de servidores web que hospeda la página de acceso telefónico local. El usuario debe dirigirse a la página de acceso telefónico. También puede confirmar que su dirección de acceso telefónico simple funciona correctamente. Un ejemplo de una dirección URL simple para el acceso telefónico eshttps://dialin.contoso.com
    
      - Para confirmar que la dirección URL de detección automática funciona, https://lyncdiscoverescriba. externaldomainFQDN. El explorador debe pedirle que abra un archivo. Seleccione Bloc de notas para abrirlo. Una respuesta típica sería similar a:
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

