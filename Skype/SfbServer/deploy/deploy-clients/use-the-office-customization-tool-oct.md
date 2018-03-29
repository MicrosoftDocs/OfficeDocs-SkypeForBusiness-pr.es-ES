---
title: Usar la Herramienta de personalización de Office (OCT) en Skype Empresarial Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Resumen: Cómo utilizar la herramienta de personalización de Office con el Skype para cliente de empresa.'
ms.openlocfilehash: b0e8dd399af7a75a6f575d554cbe6c25c4e8ffd3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server-2015"></a>Usar la Herramienta de personalización de Office (OCT) en Skype Empresarial Server 2015
 
**Resumen:** Cómo utilizar la herramienta de personalización de Office con el Skype para cliente de empresa.
  
La herramienta de personalización de Office (OCT) forma parte del programa de instalación y es la herramienta recomendada para muchas personalizaciones. Mediante el uso de la herramienta OCT, personalizar Office y guardar las personalizaciones en un archivo .msp de personalización de instalación. Coloque el archivo en la carpeta actualizaciones del punto de instalación de red. Al instalar Office, el programa de instalación busca un archivo de personalización del programa de instalación en la carpeta actualizaciones y aplica las personalizaciones. La carpeta de actualizaciones puede utilizarse sólo para implementar actualizaciones de software durante una instalación inicial de Office.
  
Los PTU es parte de la instalación y se utiliza únicamente para las versiones de licencia por volumen del producto. Para ejecutar OCT escribiendo `setup.exe /admin` en la línea de comandos desde la raíz del punto de instalación de red que contiene la oficina de los archivos de origen. Por ejemplo, use lo siguiente:
  
 `\\server\share\Office15\setup.exe /admin`
  
Los administradores utilizan la herramienta OCT para crear un archivo .msp de personalización de instalación y puede personalizar las siguientes áreas:
  
- **Programa de instalación** Se utiliza para especificar la ubicación de instalación predeterminada en el cliente y organización el nombre predeterminado, los orígenes de instalación de red adicional, clave de producto, contrato de licencia de usuario final, Mostrar nivel de versiones anteriores de Office para quitar los programas personalizados que se ejecutarán durante instalación, configuración de seguridad y las propiedades de instalación.
    
- **Características** Se utiliza para configurar opciones de usuario y personalizar cómo se instalan las características de Office. Los administradores pueden usar la OCT para especificar los valores iniciales predeterminados de la aplicación de Office para los usuarios. Los usuarios pueden modificar la mayoría de las opciones después de la instalación.
    
- **Contenido adicional** Se utiliza para agregar o quitar archivos, agregar o quitar entradas del registro y configurar accesos directos.
    
- **Outlook** Se utiliza para personalizar el perfil predeterminado de Outlook de un usuario, especificar la configuración de Exchange, agregar cuentas, quitar cuentas y exportar la configuración y especificar grupos de envío y recepción.
    
Para obtener información acerca de los PTU, consulte [utilizar la herramienta OCT para personalizar Office 2013](https://technet.microsoft.com/library/cc179132.aspx). Tenga en cuenta que esta información también se aplica a Office 2016.
  

