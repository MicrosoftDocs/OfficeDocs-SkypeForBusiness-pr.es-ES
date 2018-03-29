---
title: Director General configuración del Ampliador
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 'Para modificar la configuración de un Director existente, se presentan con las siguientes secciones:'
ms.openlocfilehash: e806f917dbcfe3e626410d3bb76caad3c40ed5d3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="director-general-settings-expander"></a>Director General configuración del Ampliador
 
Para modificar la configuración de un Director existente, se presentan con las siguientes secciones:
  
- Configuración general
    
- Servicios web
    
## 

### <a name="general-settings"></a>Configuración general

Nombre de dominio completo (FQDN) del grupo de Director. Edite el FQDN del servidor para cambiar el valor correspondiente. Necesita haber un registro host (A) de DNS que coincida con el nuevo valor.
  
En **Asociaciones**, puede editar o especificar lo siguiente:
  
Recurso compartido de archivos para el grupo de Director que desee utilizar. Seleccione un recurso de archivo existente que ya se ha definido en el generador de topología, o haga clic en **nuevo** para crear una nueva definición de recurso compartido de archivo.
  
Supervisión de almacén de SQL Server.
  
> [!IMPORTANT]
> Antes de publicar la nueva topología que se ha definido, el servidor especificado necesitará existir y estar incorporado en el dominio. Si ha creado un nuevo recurso compartido de archivo, debe crearse el recurso compartido de archivos en el servidor que usted designe. 
  
### <a name="web-services"></a>Servicios web

Para modificar o especificar opciones adicionales para los servicios Web en el grupo de directores, modificar o especificar la configuración de los servicios de Web interno y los servicios Web externos.
  
Para **servicios web de interno** puede especificar lo siguiente:
  
> [!CAUTION]
> Si tiene más de un grupo de servidores Front-End o servidor Front-End los servicios Web externos FQDN debe ser único. Por ejemplo, si define el FQDN de un servidor Front-End de servicios Web externos como **pool01.contoso.com**, no puede utilizar **pool01.contoso.com** para otro grupo de servidores Front-End o un servidor Front-End. Si también está implementando directores, externo FQDN definido para cualquier Director de los servicios Web o grupo de directores debe ser única de cualquier otro Director o Director pool, así como cualquier grupo de servidores Front-End o un servidor Front-End. Si decide reemplazar los servicios web interno con un FQDN de definición propia, cada FQDN debe ser único de cualquier otro grupo de servidores frontales, Director o un grupo de directores.
  
Si selecciona reemplazar FQDN, puede especificar un FQDN diferente para la identidad de servicios de Web interno en el grupo. De forma predeterminada, la configuración es el nombre del grupo actual tal como se define para el grupo de directores.
  
Puede especificar los puertos de escucha y publicados para HTTP y HTTPS que requiere su implementación. La configuración predeterminada del puerto 80 para HTTP y el puerto 443 para HTTPS es la configuración más común y normalmente no es necesario cambiar a menos que tenga requisitos específicos dentro de su organización y el diseño de la infraestructura.
  
Para los **servicios web externos**, se puede especificar lo siguiente:
  
Puede definir el nombre de dominio completo de los servicios Web externos. El FQDN especificado aquí se definirá normalmente según los requisitos de la conexión externa, como el proxy inverso.
  
Puede especificar los puertos de escucha y publicados para HTTP y HTTPS que requiere su implementación. La configuración predeterminada del puerto 8080 para HTTP y el puerto 4443 para HTTPS se define inicialmente. Puede cambiar estos valores para los puertos de escucha en función de los requisitos de proxy inverso y de red externa. Los puertos publicados se establecen en el valor predeterminado es el puerto 80 para HTTP y el puerto 443 para HTTPS. Estos valores determinan qué puertos del grupo Director o servidor Director escuchará las solicitudes entrantes. Normalmente, estos no es necesario cambiarlo, a menos que haya conflicto de requisitos de puerto en el grupo. Se esperan que puertos publicados internos y externos que utilizan los mismos valores de puerto. No es un conflicto.
  

