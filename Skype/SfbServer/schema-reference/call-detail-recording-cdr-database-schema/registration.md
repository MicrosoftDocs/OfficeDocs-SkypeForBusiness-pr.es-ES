---
title: Tabla Registration
ms.reviewer: ''
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
ms.openlocfilehash: 1dd8f623799753e078d112d08de960076618dfac
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885686"
---
# <a name="registration-table"></a>Tabla Registration
 
Cada registro representa un evento de registro de usuario.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Hora de la solicitud de sesión. Se utiliza en forma conjunta con **SessionIdSeq** para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**UserId** <br/> |int  <br/> |Externa  <br/> |El identificador de usuario. Consulte la [tabla de los usuarios](users.md) para obtener más información. <br/> |
|**Valor EndpointId** <br/> |uniqueidentifier  <br/> ||Un GUID para identificar un extremo de registro. Normalmente, el evento de registro desde el mismo equipo del mismo usuario tendrá el mismo identificador de extremo. Equipos diferentes tienen un identificador de extremo diferente.  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||Identificador que se usa para diferenciar los registros con el mismo usuario y el mismo extremo.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Externa  <br/> |Versión de cliente del usuario actual. Consulte la [tabla ClientVersions en Skype para Business Server 2015](clientversions.md) para obtener más información. <br/> |
|**RegistrarId** <br/> |int  <br/> |Externa  <br/> |Identificador del servidor de registrador que se utilizan para el registro. Consulte la [tabla de servidores](servers.md) para obtener más información. <br/> |
|**PoolId** <br/> |int  <br/> |Externa  <br/> |Identificador del grupo de servidores en el que se ha capturado la sesión. Vea la [tabla de grupos de servidores](pools.md) para obtener más información. <br/> |
|**EdgeServerId** <br/> |int  <br/> |Externa  <br/> |Servidor perimetral el registro se va a través de. Consulte la [tabla EdgeServers en Skype para Business Server 2015](edgeservers.md) para obtener más información. <br/> |
|**IsInternal** <br/> |Bit  <br/> ||Si el usuario se registra desde interna o no.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||Si UserService está disponible o no.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||Si registrar con el registrador principal o no.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||Indica si el usuario está registrado con una aplicación de sucursal con funciones de supervivencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||Hora de registro.  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||Anulación del registro tiempo.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Código de respuesta de la solicitud de registro.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||Identificador de diagnóstico de la solicitud de registro. Esto indica que ese tipo de información de diagnóstico.  <br/> |
|**DeviceId** <br/> |int  <br/> |Externa  <br/> |El dispositivo que proviene la solicitud de registro. Consulte la [tabla de dispositivos en Skype para Business Server 2015](devices.md) para obtener más información. <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Externa  <br/> |La razón de de-register, como 'iniciada por el usuario', 'registro expirado', 'error de cliente' y mucho más. Consulte la [tabla DeRegisterType en Skype para Business Server 2015](deregistertype.md) para obtener más información. <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||Dirección IP del extremo del usuario registrado con. Esto puede ser una dirección IPv4 o una dirección IPv6.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   

