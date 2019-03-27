---
title: Tabla de las conferencias en Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Cada registro de esta tabla contiene detalles de llamadas sobre una conferencia.
ms.openlocfilehash: f0401c150f3835772ba0df20f8c02c64c9919921
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881956"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Tabla de las conferencias en Skype para Business Server 2015
 
Cada registro de esta tabla contiene detalles de llamadas sobre una conferencia.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Hora en que la solicitud de conferencia que se ha capturado por el agente de CDR. Se utiliza sólo como una clave principal para identificar de forma exclusiva una instancia de la conferencia.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una instancia de la conferencia. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Externa  <br/> |URI de conferencia. Consulte la [tabla ConferenceUris en Skype para Business Server 2015](conferenceuris.md) para obtener más información. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |Útil para conferencias periódicas; cada instancia de una conferencia periódica tiene el mismo **URI de conferencia**, pero tendrá un **ConfInstance**de diferente. <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |Hora de inicio de la conferencia.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |Hora de inicio de la conferencia.  <br/> |
|**PoolId** <br/> |int  <br/> |Externa  <br/> |Número de identificador para identificar el grupo en el que se ha capturado la conferencia. Vea la [tabla de grupos de servidores](pools.md) para obtener más información. <br/> |
|**OrganizerId** <br/> |Int  <br/> |Externa  <br/> |Número de identificador para identificar el URI de esta conferencia del organizador. Consulte la [tabla de los usuarios](users.md) para obtener más información. <br/> |
|**Marca** <br/> |smallint  <br/> || Una máscara de bits que contiene los atributos de conferencia. Los valores posibles son: <br/>  0 x 01 <br/>  Sintéticas <br/>  Transacciones <br/> |
|**Procesar** <br/> |bit  <br/> ||Campo interno que usa el servicio de supervisión.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   
\*Para la mayoría de las sesiones, SessionIdSeq tendrá el valor de 1. Si inicia dos sesiones exactamente al mismo tiempo, la SessionIdSeq para uno será 1, y para la otra va a ser 2 y así sucesivamente.
  

