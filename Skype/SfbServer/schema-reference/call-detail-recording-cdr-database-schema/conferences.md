---
title: Mesa de conferencias en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Cada registro de esta tabla contiene los detalles de la llamada acerca de una conferencia.
ms.openlocfilehash: f0d90f7abb99bce012e864fa2485386c335de409
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Mesa de conferencias en Skype para Business Server 2015
 
Cada registro de esta tabla contiene los detalles de la llamada acerca de una conferencia.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Tiempo que la solicitud de conferencia fue capturada por el agente de CDR. Se utiliza sólo como una clave principal para identificar de forma exclusiva una instancia de la conferencia.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una instancia de la conferencia. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Externa  <br/> |Conferencia de URI. Consulte la [tabla ConferenceUris en Skype para Business Server 2015](conferenceuris.md) para obtener más información. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |Útil para conferencias periódicas; cada instancia de una conferencia periódica tiene el mismo **ConferenceUri**, pero tendrá una diferente **ConfInstance**. <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |Hora de inicio de la conferencia.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |Hora de inicio de la conferencia.  <br/> |
|**PoolId** <br/> |int  <br/> |Externa  <br/> |Número de ID para identificar el grupo en el que se ha capturado la conferencia. Consulte la [tabla de grupos](pools.md) para obtener más información. <br/> |
|**OrganizerId** <br/> |Int  <br/> |Externa  <br/> |Número de ID para identificar el URI de esta conferencia multimedia. Consulte la [tabla de usuarios](users.md) para obtener más información. <br/> |
|**Indicador** <br/> |smallint  <br/> || Una máscara de bits que contiene los atributos de la conferencia. Los posibles valores son: <br/>  0 x 01 <br/>  Sintético <br/>  Transacción <br/> |
|**Procesado** <br/> |bit  <br/> ||Campo interno utilizado por el servicio de supervisión.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   
\*Para la mayoría de las sesiones SessionIdSeq tendrá el valor 1. Si dos sesiones empiezan en exactamente al mismo tiempo, el SessionIdSeq para uno será 1 y para el otro será 2 y así sucesivamente.
  

