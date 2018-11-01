---
title: 'Lync Server 2013: Comprobar el acceso a través del proxy inverso'
TOCTitle: Comprobar el acceso a través del proxy inverso
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48274841
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar el acceso a través del proxy inverso en Lync Server 2013

 

_**Última modificación del tema:** 2013-03-29_

Realice el siguiente procedimiento para comprobar que los usuarios pueden obtener acceso a la información sobre el proxy inverso. Puede que tenga que completar la configuración del firewall y del Sistema de nombres de dominio (DNS) para que el acceso funcione correctamente.

## Para comprobar que puede obtener acceso al sitio web a través de Internet

  - Abra un explorador web y escriba las direcciones URL en la barra **Dirección** que utilizan los clientes para obtener acceso a los archivos de Libreta de direcciones y al sitio web para conferencias, tal como se indica a continuación:
    
      - Para un servidor de la libreta de direcciones, escriba una dirección URL similar a la siguiente: **https:// *externalwebfarmFQDN* /abs**, donde *externalwebfarmFQDN* es el FQDN externo de la granja de servidores web que hospeda los archivos del servidor de la libreta de direcciones. El usuario debe recibir un desafío HTTP, ya que la seguridad de directorios de la carpeta del servidor de la Libreta de direcciones está configurada para la autenticación de Windows de forma predeterminada.
    
      - Para las conferencias, escriba una dirección URL similar a la siguiente: **https:// *externalwebfarmFQDN* /meet**, donde *externalwebfarmFQDN* es el FQDN externo de la granja de servidores web que hospeda el contenido de reuniones. Esta dirección URL debe mostrar la página de solución de problemas para conferencias. Alternativamente, confirme que su dirección URL sencilla para conferencias funciona correctamente. Un ejemplo de dirección URL sencilla para conectarse a una conferencia es https://meet.contoso.com
    
      - Para la expansión de grupos de distribución, escriba una dirección URL similar a la siguiente: **https:// *externalwebfarmFQDN* /GroupExpansion/service.svc**. El usuario debe recibir un desafío HTTP, ya que la seguridad de directorios del servicio de expansión de grupos de distribución está configurada de forma predeterminada para la autenticación de Windows.
    
      - Como acceso telefónico local, escriba una dirección URL sencilla similar a la siguiente **https:// *externalwebfarmFQDN* /dialin**, donde *externalwebfarmFQDN* es el FQDN externo de la granja de servidores web que hospeda la página de acceso telefónico local para las conferencias de acceso telefónico. Se dirigirá al usuario a la página de acceso telefónico local. Alternativamente, confirme que el acceso telefónico local de su dirección URL sencilla funciona correctamente. Una dirección URL sencilla de ejemplo para acceso telefónico local podría ser https://dialin.contoso.com
    
      - Para confirmar que la dirección URL de detección automática está funcionando, escriba https://lyncdiscover. *externaldomainFQDN* . El explorador debería preguntarle antes de abrir un archivo. Seleccione Bloc de notas para abrirlo. Una respuesta típica sería similar a la siguiente:
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

