---
title: Tabla de conferencias
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
ms.openlocfilehash: 6dfe60a28e8279f7b4c469c61cddc28912db261eedf4754588de4bd8f5852728
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309159"
---
# <a name="conference-table"></a>Tabla de conferencias
 
La tabla Conference es una tabla auxiliar. Cada registro representa una conferencia o sesión punto a punto.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica este registro de conferencia.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |único  <br/> |ConferenceURI, si se trata de una conferencia, o DialogID, si es una sesión punto a punto.  <br/> |
|**Suma de comprobación** <br/> |Entero  <br/> |index  <br/> |Suma de comprobación del URI de conferencia. Para uso interno.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Únicamente para uso interno.  <br/> |
   

