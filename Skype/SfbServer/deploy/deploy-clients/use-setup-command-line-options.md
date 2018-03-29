---
title: Usar las opciones de la línea de comandos en Skype Empresarial Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Resumen: Conozca las operaciones de línea de comandos de Setup.exe en la instalación de Office.'
ms.openlocfilehash: 0fa4f31750697f0bd0dbe87bbde025cbc7f530bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="use-setup-command-line-options-in-skype-for-business-server-2015"></a>Usar las opciones de la línea de comandos en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre las operaciones de línea de comandos de Setup.exe en la instalación de Office.
  
La línea de comandos de Setup.exe se utiliza para muy pocas operaciones en la instalación de Office. En lugar de utilizar las opciones de línea de comandos de instalación, normalmente utilizará la herramienta de personalización de Office y el archivo Config.xml para productos de setup y la característica de personalización.
  
La línea de comandos de Setup.exe de Office reconoce las opciones de línea de comandos que se detallan en la siguiente tabla.
  
**Opciones de línea de comandos de instalación de Office**

|**Opción de línea de comandos de instalación**|**Descripción**|
|:-----|:-----|
|/admin  <br/> |Ejecuta la Herramienta de personalización del Office para crear un archivo de personalización del programa de instalación (archivo .msp).  <br/> |
|/adminfile [path]  <br/> |Aplica a la instalación el archivo de personalización del programa de instalación especificado. Puede especificar una ruta de acceso a un archivo de personalización (archivo .msp) específico o a la carpeta donde guarde los archivos de personalización.  <br/> |
|/config [path]  <br/> |Especifica el archivo Config.xml que el programa de instalación usará durante la instalación. Utilice la opción /config para especificar el archivo Config.xml que personalizó de Skype para las instalaciones de la empresa, por ejemplo:`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |Se usa con un archivo Config.xml modificado para ejecutar el programa de instalación en modo de mantenimiento y realizar cambios en una instalación de Office existente. Por ejemplo, puede utilizar el / modificar la opción de agregar o quitar Skype para funciones de negocio.  <br/> |
|/repair Skype  <br/> |Ejecuta la instalación desde el equipo del usuario para reparar Skype para el negocio.  <br/> |
|/uninstall Skype  <br/> |Ejecuta la instalación para quitar Skype para el negocio desde el equipo del usuario.  <br/> |
   
Para obtener más información acerca de cómo utilizar las opciones de línea de comandos de instalación, consulte [https://go.microsoft.com/fwlink/p/?linkid=267515](https://go.microsoft.com/fwlink/p/?linkid=267515). 
  

