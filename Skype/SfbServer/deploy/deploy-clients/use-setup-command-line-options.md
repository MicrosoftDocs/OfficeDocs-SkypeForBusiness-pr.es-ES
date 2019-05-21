---
title: Usar las opciones de la línea de comandos de configuración con clientes de Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Resumen: Obtenga información sobre las operaciones de la línea de comandos de Setup. exe en el programa de instalación de Office.'
ms.openlocfilehash: 2eee24f9ae79ed2f73e23c68883f2552902fb672
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306485"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Usar las opciones de la línea de comandos de configuración con clientes de Skype empresarial
 
**Resumen:** Obtenga información sobre las operaciones de la línea de comandos de Setup. exe en el programa de instalación de Office.
  
La línea de comandos de Setup.exe se utiliza para muy pocas operaciones en la instalación de Office. En lugar de usar las opciones de la línea de comandos de configuración, normalmente usará la herramienta de personalización de Office y el archivo config. XML para la configuración del producto y la personalización de las características.
  
La línea de comandos de Setup.exe de Office reconoce las opciones de línea de comandos que se detallan en la siguiente tabla.
  
**Opciones de línea de comandos del programa de instalación de Office**

|**Opción de línea de comandos del programa de instalación**|**Descripción**|
|:-----|:-----|
|/admin  <br/> |Ejecuta la Herramienta de personalización del Office para crear un archivo de personalización del programa de instalación (archivo .msp).  <br/> |
|/adminfile [path]  <br/> |Aplica a la instalación el archivo de personalización del programa de instalación especificado. Puede especificar una ruta de acceso a un archivo de personalización (archivo .msp) específico o a la carpeta donde guarde los archivos de personalización.  <br/> |
|/config [path]  <br/> |Especifica el archivo Config.xml que el programa de instalación usará durante la instalación. Use la opción/config para especificar el archivo config. XML que ha personalizado para las instalaciones de Skype empresarial, por ejemplo:`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |Se usa con un archivo Config.xml modificado para ejecutar el programa de instalación en modo de mantenimiento y realizar cambios en una instalación de Office existente. Por ejemplo, puede usar la opción/Modify para agregar o quitar características de Skype empresarial.  <br/> |
|/repair Skype  <br/> |Ejecuta el programa de instalación desde el equipo del usuario para reparar Skype empresarial.  <br/> |
|/uninstall Skype  <br/> |Ejecuta el programa de instalación para quitar Skype empresarial del equipo del usuario.  <br/> |
   


