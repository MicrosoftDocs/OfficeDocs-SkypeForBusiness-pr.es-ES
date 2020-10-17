---
title: 'Lync Server 2013: comprobar el acceso a través del proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b8c8e4c92f0cdb9eb1b7070735882b43a308080
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518717"
---
# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a>Comprobar el acceso a través del proxy inverso en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-29_

Realice el siguiente procedimiento para comprobar que los usuarios pueden obtener acceso a la información sobre el proxy inverso. Puede que tenga que completar la configuración del firewall y del Sistema de nombres de dominio (DNS) para que el acceso funcione correctamente.

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a>Para comprobar que puede obtener acceso al sitio web a través de Internet

  - Abra un explorador web y escriba las direcciones URL en la barra **Dirección** que utilizan los clientes para obtener acceso a los archivos de Libreta de direcciones y al sitio web para conferencias, tal como se indica a continuación:
    
      - En servidor de libreta de direcciones, escriba una dirección URL similar a la siguiente: **https://externalwebfarmFQDN/abs** donde externalwebfarmFQDN es el FQDN externo de los servicios web externos que hospedan los servicios de libreta de direcciones. El usuario debe recibir un desafío HTTP, ya que la seguridad de directorios de la carpeta del servidor de la Libreta de direcciones está configurada para la autenticación de Windows de forma predeterminada.
    
      - Para conferencias, escriba una dirección URL similar a la siguiente: **https://externalwebfarmFQDN/meet** donde externalwebfarmFQDN es el FQDN externo de la granja de servidores web que hospeda el contenido de la reunión. Esta dirección URL debe mostrar la página de solución de problemas para conferencias. Alternativamente, confirme que su dirección URL sencilla para conferencias funciona correctamente. Una dirección URL sencilla de ejemplo para la combinación de conferencia puede ser https://meet.contoso.com
    
      - Para la expansión del grupo de distribución, escriba una dirección URL similar a la siguiente: **https://externalwebfarmFQDN/GroupExpansion/service.svc** . El usuario debe recibir un desafío HTTP, ya que la seguridad de directorios del servicio de expansión de grupos de distribución está configurada de forma predeterminada para la autenticación de Windows.
    
      - En el caso de acceso telefónico local, escriba la dirección URL sencilla similar a la siguiente, **https://externalwebfarmFQDN/dialin** donde externalwebfarmFQDN es el FQDN externo de la granja de servidores web que hospeda la página de acceso telefónico local para las conferencias de acceso telefónico local. Se dirigirá al usuario a la página de acceso telefónico local. Alternativamente, confirme que el acceso telefónico local de su dirección URL sencilla funciona correctamente. Un ejemplo de dirección URL sencilla para el acceso telefónico es https://dialin.contoso.com
    
      - Para confirmar que la dirección URL de detección automática funciona, escriba https://lyncdiscover . externaldomainFQDN. El explorador debe pedirle que abra un archivo. Seleccione Bloc de notas para abrirlo. Una respuesta típica sería similar a la siguiente:
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

