---
title: Tabla Registration
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: Cada registro representa un evento de registro de usuario.
ms.openlocfilehash: 87a05d49c9dbf723203bf8efe02dee7cd16550a3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="registration-table"></a>Tabla Registration
 
Cada registro representa un evento de registro de usuario.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Hora de la solicitud de sesión. Se utiliza junto con **SessionIdSeq** para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**ID de usuario** <br/> |int  <br/> |Externa  <br/> |El identificador de usuario. Consulte la [tabla de usuarios](users.md) para obtener más información. <br/> |
|**Valor EndpointId** <br/> |uniqueidentifier  <br/> ||Un GUID para identificar a un extremo de la inscripción. Normalmente, el evento de registro desde el mismo equipo del mismo usuario tendrá el mismo identificador de extremo. Equipos diferentes tienen un identificador de extremo diferente.  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||Identificador se utiliza para diferenciar los registros que implican el mismo usuario y el mismo extremo.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Externa  <br/> |Versión de cliente del usuario actual. Consulte la [tabla ClientVersions en Skype para Business Server 2015](clientversions.md) para obtener más información. <br/> |
|**RegistrarId** <br/> |int  <br/> |Externa  <br/> |Id. del servidor registrador usado para el registro. Consulte la [tabla de servidores](servers.md) para obtener más información. <br/> |
|**PoolId** <br/> |int  <br/> |Externa  <br/> |Id. de la agrupación en la que fue capturada la sesión. Consulte la [tabla de grupos](pools.md) para obtener más información. <br/> |
|**EdgeServerId** <br/> |int  <br/> |Externa  <br/> |El servidor perimetral del registro va a través. Consulte la [tabla EdgeServers en Skype para Business Server 2015](edgeservers.md) para obtener más información. <br/> |
|**IsInternal** <br/> |Bit  <br/> ||Si el usuario está iniciado sesión desde interno o no.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||Si la UserService está disponible o no.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||Si se registran con el registrador principal o no.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||Indica si el usuario está registrado con un dispositivo de la rama que sobreviven.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||Hora de registro.  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||Anulación de registro de tiempo.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Código de respuesta de la solicitud de registro.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID. de la solicitud de registro de diagnóstico. Esto indica que ese tipo de información de diagnóstico.  <br/> |
|**DeviceId** <br/> |int  <br/> |Externa  <br/> |El dispositivo que proviene la solicitud de registro. Consulte la [tabla de dispositivos en Skype para Business Server 2015](devices.md) para obtener más información. <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Externa  <br/> |El motivo de de-register como 'iniciada por el usuario', 'registro ha caducado', 'error de cliente' y mucho más. Consulte la [tabla DeRegisterType en Skype para Business Server 2015](deregistertype.md) para obtener más información. <br/> |
|**Dirección IP** <br/> |nvarchar(256)  <br/> ||Dirección IP del extremo del usuario registrado con. Esto puede ser una dirección IPv4 o una dirección IPv6.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   

