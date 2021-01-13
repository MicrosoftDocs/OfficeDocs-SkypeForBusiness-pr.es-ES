---
title: Tabla Conference
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La tabla Conference es una tabla auxiliar. Cada registro representa una conferencia o sesión punto a punto.
ms.openlocfilehash: 3840ad9bb4f9b0ff0aea5068c73d307d5bd0cf5e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802790"
---
# <a name="conference-table"></a>Tabla Conference
 
La tabla Conference es una tabla auxiliar. Cada registro representa una conferencia o sesión punto a punto.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |entero  <br/> |Principal  <br/> |Número único que identifica este registro de conferencia.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |único  <br/> |ConferenceURI, si se trata de una conferencia, o DialogID, si es una sesión punto a punto.  <br/> |
|**Suma de comprobación** <br/> |entero  <br/> |index  <br/> |Suma de comprobación del URI de conferencia. Para uso interno.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Únicamente para uso interno.  <br/> |
   

