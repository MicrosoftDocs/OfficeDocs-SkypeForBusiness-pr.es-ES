---
title: Tabla CallType en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: La tabla CallType es una tabla estática donde se almacena la lista de posibles tipos de llamada.
ms.openlocfilehash: 05bfcf5b13735a460f8122fc6b1ce5eeddf94b97
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743196"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Tabla CallType en Skype Empresarial Server 2015
 
La tabla CallType es una tabla estática donde se almacena la lista de posibles tipos de llamada.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |Entero  <br/> |Principal  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valores permitidos: <br/>  0 -- Desconocido <br/>  1- Mensajería instantánea <br/>  2: Uso compartido de aplicaciones <br/>  3 -- Audio <br/>  4- Audio y vídeo <br/>  5- Transferencia de archivos <br/> |
   

