---
title: Tabla de registro
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: Cada registro representa un evento de registro de usuario.
ms.openlocfilehash: 1ab9c4b80d7bdbbc379c202978d7639e286128fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823120"
---
# <a name="registration-table"></a>Tabla de registro
 
Cada registro representa un evento de registro de usuario.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, Exterior  <br/> |Hora de la solicitud de sesión. Se usa junto con **SessionIdSeq** para identificar una sesión de manera exclusiva. Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |entero  <br/> |Principal, Exterior  <br/> |Número del identificador para identificar la sesión. Se usa en combinación con **SessionIdTime** para identificar de forma única una sesión. Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**UserId** <br/> |entero  <br/> |Externo  <br/> |Identificador de usuario. Vea la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> ||GUID para identificar un extremo de registro. Por lo general, el evento de registro del mismo equipo y del mismo usuario tendrá el mismo identificador de extremo. Los equipos diferentes tienen un identificador de extremo distinto.  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||Id. usado para diferenciar registros que implican al mismo usuario y al mismo extremo.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ClientVersionId** <br/> |entero  <br/> |Externo  <br/> |Versión de cliente del usuario actual. Consulte la [tabla ClientVersions en Skype Empresarial Server 2015](clientversions.md) para obtener más información. <br/> |
|**RegistrarId** <br/> |entero  <br/> |Externo  <br/> |Identificador del servidor registrador utilizado para el registro. Vea la [tabla Servidores para](servers.md) obtener más información. <br/> |
|**PoolId** <br/> |entero  <br/> |Externo  <br/> |Identificador del grupo en el que se capturó la sesión. Vea la tabla [Grupos de](pools.md) servidores para obtener más información. <br/> |
|**EdgeServerId** <br/> |entero  <br/> |Externo  <br/> |Servidor perimetral que se utiliza para el registro. Consulte la [tabla EdgeServers en Skype Empresarial Server 2015](edgeservers.md) para obtener más información. <br/> |
|**IsInternal** <br/> |Bit  <br/> ||Si el usuario inició sesión de forma interna o no.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||Si UserService está disponible o no.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||Si el registro se realizó con el registrador principal o no.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||Indica si el usuario se registra o no con una aplicación de sucursal con funciones de supervivencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||Hora de registro.  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||Hora de anulación del registro.  <br/> |
|**ResponseCode** <br/> |entero  <br/> ||Código de respuesta de la solicitud de registro.  <br/> |
|**DiagnosticId** <br/> |entero  <br/> ||Identificador de diagnóstico de la solicitud de registro. Indica ese tipo de información de diagnóstico.  <br/> |
|**DeviceId** <br/> |entero  <br/> |Externo  <br/> |Dispositivo del cual proviene la solicitud de registro. Vea la [tabla Dispositivos en Skype Empresarial Server 2015](devices.md) para obtener más información. <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Externo  <br/> |El motivo de la desinscripción, como "usuario iniciado", "el registro ha expirado", "error de cliente" y mucho más. Consulte la [tabla DeRegisterType en Skype Empresarial Server 2015](deregistertype.md) para obtener más información. <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||Dirección IP del extremo con el que está registrado el usuario. Esta puede ser una dirección IPv4 o una dirección IPv6.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype Empresarial Server 2015.  <br/> |
   

