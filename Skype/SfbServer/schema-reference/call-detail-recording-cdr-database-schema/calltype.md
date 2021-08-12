---
title: Tabla CallType en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: La tabla CallType es una tabla estática donde se almacena la lista de posibles tipos de llamada.
ms.openlocfilehash: d5dce646dfff73d9935aba568827e21671daf4073721f8b892f369d62348e945
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296969"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Tabla CallType en Skype Empresarial Server 2015
 
La tabla CallType es una tabla estática donde se almacena la lista de posibles tipos de llamada.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |Entero  <br/> |Principal  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valores permitidos: <br/>  0 -- Desconocido <br/>  1- Mensajería instantánea <br/>  2: Uso compartido de aplicaciones <br/>  3 -- Audio <br/>  4- Audio y vídeo <br/>  5- Transferencia de archivos <br/> |
   

