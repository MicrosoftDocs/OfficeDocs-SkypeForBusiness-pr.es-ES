---
title: Tabla conferencias en Skype Empresarial Server 2015
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
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Cada registro de esta tabla contiene detalles de llamadas sobre una conferencia.
ms.openlocfilehash: d7079097b3eb29999d00a44b23f05127daf95ee4ad1eb87097ec9e77a93682b5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343264"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Tabla conferencias en Skype Empresarial Server 2015
 
Cada registro de esta tabla contiene detalles de llamadas sobre una conferencia.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal  <br/> |Hora en la que el agente de CDR capturó la solicitud de conferencia. Se usa solo como clave principal para identificar de forma única una instancia de conferencia.  <br/> |
|**SessionIdSeq** <br/> |Entero  <br/> |Principal  <br/> |Número de identificador para identificar la sesión. Se usa junto con **SessionIdTime para** identificar de forma única una instancia de conferencia. * <br/> |
|**ConferenceUriId** <br/> |Entero  <br/> |Externo  <br/> |URI de conferencia. Vea la [tabla ConferenceUris de Skype Empresarial Server 2015](conferenceuris.md) para obtener más información. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |Útil para conferencias periódicas; cada instancia de una conferencia periódica tiene el mismo **ConferenceUri**, pero tendrá un **ConfInstance diferente.** <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |Hora de inicio de la conferencia.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |Hora de inicio de la conferencia.  <br/> |
|**PoolId** <br/> |Entero  <br/> |Externo  <br/> |Número de identificador para identificar el grupo en el que se capturó la conferencia. Vea la [tabla Grupos de servidores](pools.md) para obtener más información. <br/> |
|**OrganizerId** <br/> |Int  <br/> |Externo  <br/> |Número de identificador para identificar el URI del organizador de esta conferencia. Consulta la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**Flag** <br/> |smallint  <br/> || Máscara de bits que contiene atributos de conferencia. Los valores posibles son: <br/>  0X01 <br/>  Synthetic <br/>  Transacción <br/> |
|**Procesado** <br/> |bit  <br/> ||Campo interno usado por el servicio de supervisión.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype Empresarial Server 2015.  <br/> |
   
\* Para la mayoría de las sesiones, SessionIdSeq tendrá el valor de 1. Si dos sesiones comienzan exactamente al mismo tiempo, sessionIdSeq para una será 1, y para la otra será 2, y así sucesivamente.
  

