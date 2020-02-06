---
title: Vista conferencias
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: La vista conferencias almacena información sobre las conferencias. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: 9f9448769256bfb05e6552a41c2521defa65ded0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815368"
---
# <a name="conferences-view"></a>Vista conferencias
 
La vista conferencias almacena información sobre las conferencias. Esta vista se presentó en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificación para identificar la sesión. Se usa en conjunción con SessionIdTime para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |URI de la Conferencia.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI de la Conferencia. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**ConfInstance** <br/> |identificador  <br/> |Se usa para conferencias periódicas. Cada instancia de una conferencia periódica tiene el mismo ConferenceUri pero un ConfInstance diferente.  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |Hora de inicio de la Conferencia.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |Hora de finalización de la Conferencia.  <br/> |
|**OrganizerUri** <br/> |nvarchar (450)  <br/> |Identificador URI del usuario que organizó la Conferencia.  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que organizó la Conferencia. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |Espacio empresarial del usuario que organizó la Conferencia. Para obtener más información, consulte la [tabla de inquilinos](tenants.md) . <br/> |
|**Grupo** <br/> |nvarchar(256)  <br/> |Nombre de dominio completo del grupo que ha hospedado la Conferencia.  <br/> |
|**Fdisableautoindexingonschemaupdate** <br/> |smallint  <br/> |Máscara de bits que contiene atributos de conferencia. Los valores posibles son:  <br/> 0X01: transacción sintética  <br/> |
   

