---
title: Utilice las opciones de línea de comandos del programa de instalación con Skype para clientes empresariales
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Resumen: Obtenga información sobre las operaciones de la línea de comandos de Setup.exe en el programa de instalación de Office.'
ms.openlocfilehash: d3bf2b4d867fbbb43c346f2b9572de329ec66bdc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214880"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Utilice las opciones de línea de comandos del programa de instalación con Skype para clientes empresariales
 
**Resumen:** Obtenga información acerca de las operaciones de la línea de comandos de Setup.exe en el programa de instalación de Office.
  
La línea de comandos de Setup.exe se utiliza para muy pocas operaciones en la instalación de Office. En lugar de usar las opciones de línea de comandos del programa de instalación, por lo general, debe usar la herramienta de personalización de Office y el archivo Config.xml para la personalización del programa de instalación y la característica de producto.
  
La línea de comandos de Setup.exe de Office reconoce las opciones de línea de comandos que se detallan en la siguiente tabla.
  
**Opciones de línea de comandos del programa de instalación de Office**

|**Opción de línea de comandos del programa de instalación**|**Descripción**|
|:-----|:-----|
|/admin  <br/> |Ejecuta la Herramienta de personalización del Office para crear un archivo de personalización del programa de instalación (archivo .msp).  <br/> |
|/adminfile [path]  <br/> |Aplica a la instalación el archivo de personalización del programa de instalación especificado. Puede especificar una ruta de acceso a un archivo de personalización (archivo .msp) específico o a la carpeta donde guarde los archivos de personalización.  <br/> |
|/config [path]  <br/> |Especifica el archivo Config.xml que el programa de instalación usará durante la instalación. Use la opción /config para especificar el archivo Config.xml que personalizó para Skype para las instalaciones de negocio, por ejemplo:`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |Se usa con un archivo Config.xml modificado para ejecutar el programa de instalación en modo de mantenimiento y realizar cambios en una instalación de Office existente. Por ejemplo, puede usar el / modificar opción para agregar o quitar Skype para las características de negocio.  <br/> |
|/repair Skype  <br/> |Ejecuta el programa de instalación desde el equipo del usuario para reparar Skype para la empresa.  <br/> |
|/uninstall Skype  <br/> |Se ejecuta el programa de instalación para quitar Skype para la empresa desde el equipo del usuario.  <br/> |
   


