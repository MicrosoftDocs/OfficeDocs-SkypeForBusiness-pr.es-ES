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
ms.localizationpriority: medium
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La tabla Conference es una tabla auxiliar. Cada registro representa una conferencia o sesión punto a punto.
ms.openlocfilehash: 3da2ed90cbb55e44d4eb4ff4902898eed6099f2e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609157"
---
# <a name="conference-table"></a>Tabla de conferencias
 
La tabla Conference es una tabla auxiliar. Cada registro representa una conferencia o sesión punto a punto.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica este registro de conferencia.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |único  <br/> |ConferenceURI, si se trata de una conferencia, o DialogID, si es una sesión punto a punto.  <br/> |
|**Suma de comprobación** <br/> |Entero  <br/> |index  <br/> |Suma de comprobación del URI de conferencia. Para uso interno.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Únicamente para uso interno.  <br/> |
   

