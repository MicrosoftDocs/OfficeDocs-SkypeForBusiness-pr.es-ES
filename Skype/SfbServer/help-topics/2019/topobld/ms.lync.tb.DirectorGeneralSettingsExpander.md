---
title: Expansor de configuración general de director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar la configuración de un director existente, se muestran las siguientes secciones:'
ms.openlocfilehash: 92d0026f2bc769f32ca635435cd71866efb75d3e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280542"
---
# <a name="director-general-settings-expander"></a>Expansor de configuración general de director
 
Para editar la configuración de un director existente, se muestran las siguientes secciones:
  
- Configuración general
    
- Servicios web
    

## <a name="general-settings"></a>Configuración general

Nombre de dominio completo (FQDN) del grupo de directores. Edite el FQDN del servidor para cambiar el valor correspondiente. Necesita haber un registro host (A) de DNS que coincida con el nuevo valor.
  
En **Asociaciones**, puede editar o especificar lo siguiente:
  
Recurso compartido de archivos para el grupo de directores que se va a usar. Seleccione un recurso compartido de archivos existente que ya se haya definido en el generador de topología o haga clic en **nuevo** para crear una nueva definición de recurso compartido de archivos.
  
Supervisar el almacén de SQL Server.
  
> [!IMPORTANT]
> Antes de publicar la nueva topología que se ha definido, el servidor especificado necesitará existir y estar incorporado en el dominio. Si ha creado un nuevo recurso compartido de archivos, el recurso compartido de archivos debe crearse en el servidor que designe. 
  
## <a name="web-services"></a>Servicios web

Para editar o especificar la configuración adicional de los servicios web en el grupo de directores, modifique o especifique la configuración de los servicios Web internos y los servicios web externos.
  
Para los **servicios Web internos** , puede especificar lo siguiente:
  
> [!CAUTION]
> Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único. Por ejemplo, si define el FQDN de los servicios web externos de un servidor front-end como **pool01.contoso.com**, no puede usar **pool01.contoso.com** para otro grupo de servidores front-end o servidor front-end. Si también va a implementar directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro grupo de directores o directores, así como de cualquier grupo de servidores front-end o servidor front-end. Si decide omitir los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único de cualquier otro grupo de servidores front-end, director o grupo de directores.
  
Si selecciona FQDN de reemplazo, puede especificar un nombre de dominio completo distinto para la identidad de Servicios web internos en el grupo de servidores. De forma predeterminada, la configuración es el nombre de la sección actual definido para el grupo de directores.
  
Puede especificar puertos de escucha y publicados para HTTP y HTTPS que requiere su implementación. La configuración predeterminada del puerto 80 para HTTP y el puerto 443 para HTTPS son las opciones más comunes y, por lo general, no es necesario cambiarlos a menos que se cumplan los requisitos específicos dentro del diseño de la infraestructura y la organización.
  
Para los **servicios web externos**, puede especificar lo siguiente:
  
Puede definir el FQDN de los servicios web externos. El FQDN especificado aquí se definirá normalmente según los requisitos de la conexión externa, como el proxy inverso.
  
Puede especificar puertos de escucha y publicados para HTTP y HTTPS que requiere su implementación. La configuración predeterminada del puerto 8080 para HTTP y el puerto 4443 para HTTPS se define inicialmente. Puede cambiar estos valores para los puertos de escucha en función de los requisitos de proxy inverso y de red externa. Los puertos publicados se establecen en los valores predeterminados del puerto 80 para HTTP y el puerto 443 para HTTPS. Estos valores determinan qué puertos el grupo de directores o el servidor de directores escuchará las solicitudes entrantes. Normalmente, no es necesario cambiar estas opciones, a menos que haya conflictos de requisitos de puertos en el grupo. Se esperan los puertos publicados internos y externos que usan los mismos valores de puerto. Este no es un conflicto.
  

