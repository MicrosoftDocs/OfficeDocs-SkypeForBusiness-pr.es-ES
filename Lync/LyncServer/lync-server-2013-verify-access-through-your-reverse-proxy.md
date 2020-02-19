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
ms.openlocfilehash: a1b26afb358a78e18476efbebf7de4c8088e131f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a>Comprobar el acceso a través del proxy inverso en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-29_

Realice el siguiente procedimiento para comprobar que los usuarios pueden obtener acceso a la información sobre el proxy inverso. Puede que tenga que completar la configuración del firewall y del Sistema de nombres de dominio (DNS) para que el acceso funcione correctamente.

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a>Para comprobar que puede obtener acceso al sitio web a través de Internet

  - Abra un explorador web y escriba las direcciones URL en la barra **Dirección** que utilizan los clientes para obtener acceso a los archivos de Libreta de direcciones y al sitio web para conferencias, tal como se indica a continuación:
    
      - En servidor de libreta de direcciones, escriba una dirección URL similar a **https://externalwebfarmFQDN/abs** la siguiente: donde externalwebfarmFQDN es el FQDN externo de los servicios web externos que hospedan los servicios de libreta de direcciones. El usuario debe recibir un desafío HTTP, ya que la seguridad de directorios de la carpeta del servidor de la Libreta de direcciones está configurada para la autenticación de Windows de forma predeterminada.
    
      - Para conferencias, escriba una dirección URL similar a la siguiente **https://externalwebfarmFQDN/meet** : donde externalwebfarmFQDN es el FQDN externo de la granja de servidores web que hospeda el contenido de la reunión. Esta dirección URL debe mostrar la página de solución de problemas para conferencias. Alternativamente, confirme que su dirección URL sencilla para conferencias funciona correctamente. Una dirección URL sencilla de ejemplo para la combinación de conferencia puede serhttps://meet.contoso.com
    
      - Para la expansión del grupo de distribución, escriba una dirección URL similar **https://externalwebfarmFQDN/GroupExpansion/service.svc**a la siguiente:. El usuario debe recibir un desafío HTTP, ya que la seguridad de directorios del servicio de expansión de grupos de distribución está configurada de forma predeterminada para la autenticación de Windows.
    
      - En el caso de acceso telefónico local, escriba la dirección URL sencilla **https://externalwebfarmFQDN/dialin** similar a la siguiente, donde externalwebfarmFQDN es el FQDN externo de la granja de servidores web que hospeda la página de acceso telefónico local para las conferencias de acceso telefónico local. Se dirigirá al usuario a la página de acceso telefónico local. Alternativamente, confirme que el acceso telefónico local de su dirección URL sencilla funciona correctamente. Un ejemplo de dirección URL sencilla para el acceso telefónico eshttps://dialin.contoso.com
    
      - Para confirmar que la dirección URL de detección automática funciona, https://lyncdiscoverescriba. externaldomainFQDN. El explorador debe pedirle que abra un archivo. Seleccione Bloc de notas para abrirlo. Una respuesta típica sería similar a la siguiente:
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

