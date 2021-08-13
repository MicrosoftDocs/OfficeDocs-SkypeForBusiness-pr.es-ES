---
title: Usar opciones de línea de comandos de instalación con Skype Empresarial cliente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Resumen: obtenga información sobre Setup.exe de línea de comandos en Office instalación.'
ms.openlocfilehash: 1eb0a6b1e2050eb7152ff0eb65c7c08af57e307f5253a8ec8502fd3e7718aa3a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300356"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Usar opciones de línea de comandos de instalación con Skype Empresarial cliente
 
**Resumen:** Obtenga información sobre Setup.exe de línea de comandos en Office instalación.
  
La línea de comandos de Setup.exe se utiliza para muy pocas operaciones en la instalación de Office. En lugar de usar las opciones de línea de comandos del programa de instalación, normalmente usará la herramienta de personalización de Office y el archivo Config.xml para la configuración del producto y la personalización de características.
  
La línea de comandos de Setup.exe de Office reconoce las opciones de línea de comandos que se detallan en la siguiente tabla.
  
**Opciones de línea de comandos del programa de instalación de Office**

|**Opción de línea de comandos del programa de instalación**|**Description**|
|:-----|:-----|
|/admin  <br/> |Ejecuta la Herramienta de personalización del Office para crear un archivo de personalización del programa de instalación (archivo .msp).  <br/> |
|/adminfile [path]  <br/> |Aplica a la instalación el archivo de personalización del programa de instalación especificado. Puede especificar una ruta de acceso a un archivo de personalización (archivo .msp) específico o a la carpeta donde guarde los archivos de personalización.  <br/> |
|/config [path]  <br/> |Especifica el archivo Config.xml que usa el programa de instalación durante la instalación. Use la opción /config para especificar el archivo Config.xml personalizado para Skype Empresarial instalaciones, por ejemplo:`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |Se utiliza con un archivo Config.xml modificado para ejecutar el programa de instalación en modo de mantenimiento y hacer cambios en una instalación de Office existente. Por ejemplo, puede usar la opción /modify para agregar o quitar Skype Empresarial características.  <br/> |
|/repair Skype  <br/> |Ejecuta el programa de instalación desde el equipo del usuario para reparar Skype Empresarial.  <br/> |
|/uninstall Skype  <br/> |Ejecuta el programa de instalación para Skype Empresarial del equipo del usuario.  <br/> |
   


