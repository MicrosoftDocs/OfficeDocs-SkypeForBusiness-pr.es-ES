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
ms.localizationpriority: medium
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: Cada registro representa un evento de registro de usuario.
ms.openlocfilehash: ed8ce9f160f42384548a01d2cd6c74b3b24e60f1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627782"
---
# <a name="registration-table"></a>Tabla de registro
 
Cada registro representa un evento de registro de usuario.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, Exterior  <br/> |Hora de la solicitud de sesión. Se usa junto con **SessionIdSeq** para identificar una sesión de manera exclusiva. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |Entero  <br/> |Principal, Exterior  <br/> |Número del identificador para identificar la sesión. Se usa en combinación con **SessionIdTime** para identificar de forma única una sesión. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**UserId** <br/> |Entero  <br/> |Externo  <br/> |Identificador de usuario. Consulta la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> ||GUID para identificar un extremo de registro. Por lo general, el evento de registro del mismo equipo y del mismo usuario tendrá el mismo identificador de extremo. Los equipos diferentes tienen un identificador de extremo distinto.  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||Id. usado para diferenciar registros que implican al mismo usuario y al mismo extremo.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ClientVersionId** <br/> |Entero  <br/> |Externo  <br/> |Versión de cliente del usuario actual. Vea la [tabla ClientVersions en Skype Empresarial Server 2015](clientversions.md) para obtener más información. <br/> |
|**RegistrarId** <br/> |Entero  <br/> |Externo  <br/> |Identificador del servidor registrador utilizado para el registro. Vea la [tabla Servidores para](servers.md) obtener más información. <br/> |
|**PoolId** <br/> |Entero  <br/> |Externo  <br/> |Identificador del grupo en el que se capturó la sesión. Vea la [tabla Grupos de servidores](pools.md) para obtener más información. <br/> |
|**EdgeServerId** <br/> |Entero  <br/> |Externo  <br/> |Servidor perimetral que se utiliza para el registro. Vea la [tabla EdgeServers en Skype Empresarial Server 2015](edgeservers.md) para obtener más información. <br/> |
|**IsInternal** <br/> |Bit  <br/> ||Si el usuario inició sesión de forma interna o no.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||Si UserService está disponible o no.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||Si el registro se realizó con el registrador principal o no.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||Indica si el usuario se registra o no con una aplicación de sucursal con funciones de supervivencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||Hora de registro.  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||Hora de anulación del registro.  <br/> |
|**ResponseCode** <br/> |Entero  <br/> ||Código de respuesta de la solicitud de registro.  <br/> |
|**DiagnosticId** <br/> |Entero  <br/> ||Identificador de diagnóstico de la solicitud de registro. Indica ese tipo de información de diagnóstico.  <br/> |
|**DeviceId** <br/> |Entero  <br/> |Externo  <br/> |Dispositivo del cual proviene la solicitud de registro. Consulta la [tabla Dispositivos de Skype Empresarial Server 2015](devices.md) para obtener más información. <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Externo  <br/> |El motivo de la desinscripción, como "usuario iniciado", "el registro expiró", "error de cliente" y mucho más. Vea la [tabla DeRegisterType en Skype Empresarial Server 2015](deregistertype.md) para obtener más información. <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||Dirección IP del extremo con el que está registrado el usuario. Esta puede ser una dirección IPv4 o una dirección IPv6.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype Empresarial Server 2015.  <br/> |
   

