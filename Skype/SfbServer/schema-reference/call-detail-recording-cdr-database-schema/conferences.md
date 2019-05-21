---
title: Tabla conferencias en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Cada registro de esta tabla contiene detalles de llamadas sobre una conferencia.
ms.openlocfilehash: 41a2a25e80b073b568152422defeee1ca3e2ac19
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296451"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Tabla conferencias en Skype empresarial Server 2015
 
Cada registro de esta tabla contiene detalles de llamadas sobre una conferencia.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Hora en que el agente CDR capturó la solicitud de conferencia. Solo se usa como clave principal para identificar de forma exclusiva una instancia de conferencia.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Número de identificación para identificar la sesión. Se usa junto con **SessionIdTime** para identificar de forma exclusiva una instancia de conferencia. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Extranjero  <br/> |URI de la Conferencia. Para obtener más información, consulte la [tabla ConferenceUris en Skype empresarial Server 2015](conferenceuris.md) . <br/> |
|**ConfInstance** <br/> |identificador  <br/> | <br/> |Útil para las conferencias recurrentes; cada instancia de una conferencia periódica tiene el mismo **ConferenceUri**, pero tendrá un **ConfInstance**diferente. <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |Hora de inicio de la Conferencia.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |Hora de inicio de la Conferencia.  <br/> |
|**PoolId** <br/> |int  <br/> |Extranjero  <br/> |Número de identificación para identificar el grupo en el que se capturó la Conferencia. Para obtener más información, consulte la [tabla grupos](pools.md) . <br/> |
|**OrganizerId** <br/> |ENT  <br/> |Extranjero  <br/> |Número de identificación para identificar el URI del organizador de esta conferencia. Para obtener más información, consulte la [tabla usuarios](users.md) . <br/> |
|**Fdisableautoindexingonschemaupdate** <br/> |smallint  <br/> || Máscara de bits que contiene atributos de conferencia. Los valores posibles son: <br/>  0X01 <br/>  Sintética <br/>  Transaccional <br/> |
|**Procesar** <br/> |bit  <br/> ||Campo interno usado por el servicio de supervisión.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Fechas  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype empresarial Server 2015.  <br/> |
   
\*Para la mayoría de las sesiones, SessionIdSeq tendrá el valor 1. Si dos sesiones comienzan exactamente al mismo tiempo, la SessionIdSeq para uno será 1, y la otra será 2, y así sucesivamente.
  

