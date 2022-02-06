---
title: Importar certificado (introducción)
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
description: 'Para importar un certificado, debe proporcionar la ruta del archivo del certificado. En el cuadro de texto Seleccionar archivo del certificado, puede escribir el nombre de archivo y la ruta completa, o bien hacer clic en el botón Examinar y buscar la ubicación y el nombre de archivo, que suele ser un archivo con la extensión .p7b, .pfx, o .cer.'
---

# <a name="import-certificate-intro"></a>Importar certificado (introducción)
 
Para importar un certificado, debe proporcionar la ruta del archivo del certificado. En el cuadro de texto **Seleccionar archivo del certificado**, puede escribir el nombre de archivo y la ruta completa, o bien hacer clic en el botón **Examinar** y buscar la ubicación y el nombre de archivo, que suele ser un archivo con la extensión .p7b, .pfx, o .cer.
  
Si el certificado contiene una clave privada, active la casilla **Archivo de certificado contiene la clave privada del certificado**. Si se selecciona esta casilla de verificación, se habilita la entrada de texto de **Contraseña**. Si tiene un certificado asociado con una clave privada, al crearse el certificado se suele colocar una contraseña en la clave privada. La contraseña de la clave privada se asigna para que el certificado y la clave privada puedan importarse al almacén de certificados. Tras haber facilitado la información de la ruta de archivo del certificado, y la contraseña de clave privada, si era el caso, haga clic en **Siguiente**.
  
> [!IMPORTANT]
> La importación no se realizará si no se proporciona la contraseña de clave privada. 
  

