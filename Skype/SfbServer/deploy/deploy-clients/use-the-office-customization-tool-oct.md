---
title: Usar la Herramienta de personalización de Office (OCT) en Skype Empresarial Server
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
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Resumen: cómo usar la Herramienta de personalización de Office con el cliente de Skype Empresarial.'
ms.openlocfilehash: ba99f0556f3fb1d0e0f6870d1eaa7a3d2108b4d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812570"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Usar la Herramienta de personalización de Office (OCT) en Skype Empresarial Server
 
**Resumen:** Cómo usar la Herramienta de personalización de Office con el cliente de Skype Empresarial.
  
La Herramienta de personalización de Office (OCT) forma parte del programa de instalación y es la herramienta recomendada para muchas personalizaciones. Mediante la OCT, puede personalizar Office y guardar las personalizaciones en un archivo .msp de personalización del programa de instalación. El archivo se coloca en la carpeta Actualizaciones del punto de instalación en red. Al instalar Office, el programa de instalación busca un archivo de personalización del programa de instalación en la carpeta Actualizaciones y aplica las personalizaciones. La carpeta Actualizaciones solo se puede usar para implementar actualizaciones de software durante una instalación inicial de Office.
  
La OCT forma parte de la configuración y solo se usa para las versiones con licencia por volumen del producto. Para ejecutar la OCT, escriba en la línea de comandos desde la raíz del punto de instalación de red que contiene los archivos de  `setup.exe /admin` origen de Office. Por ejemplo, utilice lo siguiente:
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
Los administradores usan la OCT para crear un archivo .msp de personalización del programa de instalación y pueden personalizar las siguientes áreas:
  
- **Instalación** Se usa para especificar la ubicación de instalación predeterminada en el cliente y el nombre predeterminado de la organización, orígenes de instalación de red adicionales, clave de producto, contrato de licencia para el usuario final, nivel de visualización, versiones anteriores de Office que se quitarán, programas personalizados que se ejecutarán durante la instalación, configuración de seguridad y propiedades del programa de instalación.
    
- **Características** Se usa para configurar las opciones de usuario y personalizar la forma en que se instalan las características de Office. Los administradores pueden utilizar la OCT para especificar los valores iniciales predeterminados de la aplicación de Office para los usuarios. Los usuarios pueden modificar la mayoría de las opciones después de la instalación.
    
- **Contenido adicional** Se usa para agregar o quitar archivos, agregar o quitar entradas del Registro y configurar accesos directos.
    
- **Outlook** Se usa para personalizar el perfil predeterminado de Outlook de un usuario, especificar la configuración de Exchange, agregar cuentas, quitar cuentas y exportar la configuración, y especificar grupos de envío o recepción.
    
Para obtener información acerca de la OCT, [vea Usar la OCT para personalizar Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)). Tenga en cuenta que esta información también se aplica a versiones posteriores de Office.
  

