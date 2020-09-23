---
title: Expansor de configuración general de director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 'Para editar la configuración de un Director existente, le presentamos las secciones siguientes:'
ms.openlocfilehash: 261593cd7b1f8f79588462cb57eb8ecc517dd4a3
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218991"
---
# <a name="director-general-settings-expander"></a>Expansor de configuración general de director
 
Para editar la configuración de un Director existente, le presentamos las secciones siguientes:
  
- Configuración general
    
- Servicios web
    


## <a name="general-settings"></a>Configuración general

Nombre de dominio completo (FQDN) del grupo de Directores. Edite el FQDN del servidor para cambiar ese valor. Debe tener un registro de host (A) de sistema de nombres de dominio (DNS) que coincida con el nuevo valor.
  
En **Asociaciones** puede editar o especificar los elementos siguientes:
  
El recurso compartido de archivos que debe usar el grupo de directores. Seleccione un recurso compartido de archivos existente que ya se haya definido en Topology Builder, o haga clic en **nuevo** para crear una nueva definición de recurso compartido de archivos.
  
Supervisión del almacén de SQL Server.
  
> [!IMPORTANT]
> Antes de publicar la topología definida recientemente, el servidor que especifique debe existir y se debe unir al dominio. Si crea un nuevo recurso compartido de archivos, debe hacerlo en el servidor que designe. 
  
## <a name="web-services"></a>Servicios web

Para editar o especificar una configuración adicional de los servicios web en el grupo de directores, debe modificar o especificar la configuración de los servicios web internos y externos.
  
En el caso de los **servicios web internos** puede especificar lo siguiente:
  
> [!CAUTION]
> Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único. Por ejemplo, si define el FQDN de servicios web externos de un servidor front-end como **pool01.contoso.com**, no puede usar **pool01.contoso.com** para otro grupo de servidores front-end o servidor front-end. Si también está implementando directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro director o grupo de directores, así como cualquier grupo de servidores front-end o servidor front-end. Si decide reemplazar los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único en cualquier otro grupo de servidores front-end, director o grupo de directores.
  
Si selecciona FQDN de reemplazo, puede especificar un FQDN distinto para la identidad de los servicios web internos en el grupo. De forma predeterminada, la configuración del nombre de grupo actual la define el grupo de directores.
  
Puede especificar los puertos de escucha y publicados para HTTP y HTTPS que requiera su implementación. La configuración predeterminada de puerto 80 para HTTP y puerto 443 para HTTPS es la más común y generalmente no es necesario cambiarla a menos que tenga su organización o el diseño de la infraestructura le marque unos requisitos específicos.
  
En el caso de los **servicios web externos**, puede especificar lo siguiente:
  
Puede definir el FQDN de los servicios web externos. El FQDN que se especifica aquí generalmente quedará definido por los requisitos externos de conexión, como el proxy inverso.
  
Puede especificar los puertos de escucha y publicados para HTTP y HTTPS que requiera su implementación. Inicialmente y de forma predeterminada la configuración es el puerto 8080 para HTTP y el puerto 4443 para HTTPS. Cambie esta configuración para los puertos de escucha en función de los requisitos del proxy inverso y de la red externa. Los puertos publicados se establecen de forma predeterminada en puerto 80 para HTTP y puerto 443 para HTTPS. Estos valores determinan qué puertos escucharán el grupo de directores o el servidor de directores para las solicitudes de entrada. Generalmente no es necesario cambiarlos, a menos que exista un conflicto de requisitos de puerto en el grupo. Es de esperar que haya puertos publicados internos y externos que usen los mismos valores de puerto. Esto no es un conflicto.
  

