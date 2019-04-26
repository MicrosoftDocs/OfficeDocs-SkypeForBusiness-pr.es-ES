---
title: Expansor de configuración general de director
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 'Para editar la configuración de un Director existente, le presentamos las secciones siguientes:'
ms.openlocfilehash: 92ddafb0029f4860f4fd36ddb9a497d21deb97d2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226888"
---
# <a name="director-general-settings-expander"></a>Expansor de configuración general de director
 
Para editar la configuración de un Director existente, le presentamos las secciones siguientes:
  
- Configuración general
    
- Servicios web
    


## <a name="general-settings"></a>Configuración general

Nombre de dominio completo (FQDN) del grupo de servidores Director. Edite el FQDN del servidor para cambiar el valor correspondiente. Necesita haber un registro host (A) de DNS que coincida con el nuevo valor.
  
En **Asociaciones**, puede editar o especificar lo siguiente:
  
Recurso compartido de archivos para el grupo de Director debe usar. Seleccione un recurso compartido archivo existente que ya se ha definido en el generador de topología, o haga clic en **nuevo** para crear una nueva definición de recurso compartido de archivo.
  
Supervisión del almacén de SQL Server.
  
> [!IMPORTANT]
> Antes de publicar la nueva topología que se ha definido, el servidor especificado necesitará existir y estar incorporado en el dominio. Si ha creado un nuevo recurso compartido de archivos, el recurso compartido de archivos debe crearse en el servidor que designe. 
  
## <a name="web-services"></a>Servicios web

Para editar o especificar opciones adicionales para los servicios Web en el grupo de directores, modificar o especificar la configuración en los servicios Web internos y los servicios Web externos.
  
Para **servicios web de interno** puede especificar lo siguiente:
  
> [!CAUTION]
> Si tiene más de un grupo de servidores Front-End o servidor Front-End los servicios Web externos FQDN debe ser único. Por ejemplo, si define el FQDN de un servidor Front-End de servicios Web externos como **pool01.contoso.com**, no puede usar **pool01.contoso.com** para otro grupo de servidores Front-End o servidor Front-End. Si va a implementar también los directores, la externa FQDN definido para cualquier Director de los servicios Web o debe ser único de cualquier otro grupo de directores Director o Director del grupo de servidores, así como cualquier otro grupo de servidores Front-End o un servidor Front-End. Si decide reemplazar los servicios web internos con un FQDN autodefinido, cada FQDN debe ser único de cualquier otro grupo de servidores Front-End, Director o un grupo de directores.
  
Si selecciona FQDN de reemplazo, puede especificar un nombre de dominio completo distinto para la identidad de Servicios web internos en el grupo de servidores. De forma predeterminada, el valor es el nombre del grupo actual, tal como se define para el grupo de directores.
  
Puede especificar los puertos de escucha y publicados para HTTP y HTTPS que requiere la implementación. La configuración predeterminada del puerto 80 para HTTP y el puerto 443 para HTTPS es la configuración más comunes y normalmente no es necesario que cambiarse a menos que tengan requisitos específicos dentro de la organización y el diseño de la infraestructura.
  
Para los **servicios web externos**, puede especificar lo siguiente:
  
Puede definir el FQDN de los servicios Web externos. El FQDN especificado aquí se definirá normalmente según los requisitos de la conexión externa, como el proxy inverso.
  
Puede especificar los puertos de escucha y publicados para HTTP y HTTPS que requiere la implementación. La configuración predeterminada del puerto 8080 para HTTP y el puerto 4443 para HTTPS se define inicialmente. Puede cambiar estos valores para los puertos de escucha en función de los requisitos de proxy inverso y de red externa. Se establecen los puertos publicados en valor predeterminado de puerto 80 para HTTP y el puerto 443 para HTTPS. Estos valores determinan qué puertos de servidor de Director o el grupo de directores escuchará para las solicitudes entrantes. Normalmente, estos no es necesario que debe cambiar, a menos que haya conflicto de los requisitos de puerto en el grupo de servidores. Se esperan puertos publicados internos y externos que usan los mismos valores de puerto. No es un conflicto.
  

