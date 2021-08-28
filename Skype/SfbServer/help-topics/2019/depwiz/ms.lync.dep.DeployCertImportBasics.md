---
title: Importar certificado (introducción)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
ROBOTS: NOINDEX, NOFOLLOW
description: Para importar un certificado, debe proporcionar la ruta del archivo del certificado. En el cuadro de texto Seleccionar archivo del certificado, puede escribir el nombre de archivo y la ruta completa, o bien hacer clic en el botón Examinar y buscar la ubicación y el nombre de archivo, que suele ser un archivo con la extensión .p7b, .pfx, o .cer.
ms.openlocfilehash: 7d3e360ee61d1262aaec8d228c5f8833d6abd3e6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616966"
---
# <a name="import-certificate-intro"></a>Importar certificado (introducción)
 
Para importar un certificado, debe proporcionar la ruta del archivo del certificado. En el cuadro de texto **Seleccionar archivo del certificado**, puede escribir el nombre de archivo y la ruta completa, o bien hacer clic en el botón **Examinar** y buscar la ubicación y el nombre de archivo, que suele ser un archivo con la extensión .p7b, .pfx, o .cer.
  
Si el certificado contiene una clave privada, active la casilla **Archivo de certificado contiene la clave privada del certificado.** Si se selecciona esta casilla de verificación, se habilita la entrada de texto de **Contraseña**. Si tiene un certificado asociado con una clave privada, al crearse el certificado se suele colocar una contraseña en la clave privada. La contraseña de la clave privada se asigna para que el certificado y la clave privada puedan importarse al almacén de certificados. Tras haber facilitado la información de la ruta de archivo del certificado, y la contraseña de clave privada, si era el caso, haga clic en **Siguiente**.
  
> [!IMPORTANT]
> La importación no se realizará si no se proporciona la contraseña de clave privada. 
  

