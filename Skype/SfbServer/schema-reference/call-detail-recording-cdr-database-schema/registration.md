---
title: Tabla Registration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: Cada registro representa un evento de registro de usuario.
ms.openlocfilehash: 7dcf96c5cb5b140711590943eb7ae5d2be8704b4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295863"
---
# <a name="registration-table"></a>Tabla Registration
 
Cada registro representa un evento de registro de usuario.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, extranjero  <br/> |Hora de la solicitud de sesión. Se usa en conjunción con **SessionIdSeq** para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, extranjero  <br/> |Número de identificación para identificar la sesión. Se usa en conjunción con **SessionIdTime** para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**Iddeusuario** <br/> |int  <br/> |Extranjero  <br/> |El identificador de usuario. Para obtener más información, consulte la [tabla usuarios](users.md) . <br/> |
|**EndpointId** <br/> |identificador  <br/> ||Un GUID para identificar un extremo de registro. Normalmente, el evento Register del mismo equipo del mismo usuario tendrá el mismo identificador de punto de conexión. Diferentes equipos tienen un identificador de extremo diferente.  <br/> |
|**EndpointEra** <br/> |Identificador  <br/> ||IDENTIFICADOR usado para diferenciar los registros que implican el mismo usuario y el mismo punto de conexión.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Extranjero  <br/> |Versión de cliente del usuario actual. Para obtener más información, consulte la [tabla ClientVersions en Skype empresarial Server 2015](clientversions.md) . <br/> |
|**RegistrarId** <br/> |int  <br/> |Extranjero  <br/> |IDENTIFICADOR del servidor del registrador usado para el registro. Para obtener más información, consulte la [tabla servidores](servers.md) . <br/> |
|**PoolId** <br/> |int  <br/> |Extranjero  <br/> |IDENTIFICADOR del grupo en el que se capturó la sesión. Para obtener más información, consulte la [tabla grupos](pools.md) . <br/> |
|**EdgeServerId** <br/> |int  <br/> |Extranjero  <br/> |Servidor perimetral en el que se está realizando la inscripción. Para obtener más información, consulte la [tabla EdgeServers en Skype empresarial Server 2015](edgeservers.md) . <br/> |
|**IsInternal** <br/> |Algo  <br/> ||Si el usuario ha iniciado sesión desde dentro o no.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||Si el UserService está disponible o no.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||Si se registra en el registrador principal o no.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||Indica si el usuario está registrado o no en un equipo de sucursal con la supervivencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||Hora de registro.  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||Hora de Desregistro.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Código de respuesta de la solicitud de registro.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||IDENTIFICADOR de diagnóstico de la solicitud de registro. Indica que el tipo de información de diagnóstico.  <br/> |
|**ID** <br/> |int  <br/> |Extranjero  <br/> |El dispositivo del que procede la solicitud de registro. Para obtener más información, consulte la [tabla dispositivos en Skype empresarial Server 2015](devices.md) . <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Extranjero  <br/> |El motivo de la anulación del registro, como "Iniciado por el usuario", "registro expirado", "error del cliente" y más. Para obtener más información, consulte la [tabla DeRegisterType en Skype empresarial Server 2015](deregistertype.md) . <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||Dirección IP del extremo con el que el usuario registró el registro. Puede ser una dirección IPv4 o una dirección IPv6.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Fechas  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype empresarial Server 2015.  <br/> |
   

