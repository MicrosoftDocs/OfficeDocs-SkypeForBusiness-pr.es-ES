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
description: 'Resumen: Cómo usar la Herramienta de personalización de Office con el cliente de Skype Empresarial.'
ms.openlocfilehash: 32cd7951690ce5b1e38c20d83c8f53a9c48cd19c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100456"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Usar la Herramienta de personalización de Office (OCT) en Skype Empresarial Server
 
**Resumen:** Cómo usar la herramienta de personalización de Office con el cliente de Skype Empresarial.
  
La Herramienta de personalización de Office (OCT) forma parte del programa de instalación y es la herramienta recomendada para muchas personalizaciones. Al usar la OCT, personaliza Office y guarda las personalizaciones en un archivo .msp de personalización del programa de instalación. El archivo se coloca en la carpeta Actualizaciones del punto de instalación en red. Al instalar Office, el programa de instalación busca un archivo de personalización del programa de instalación en la carpeta Actualizaciones y aplica las personalizaciones. La carpeta Actualizaciones solo se puede usar para implementar actualizaciones de software durante una instalación inicial de Office.
  
La OCT forma parte de la configuración y solo se usa para las versiones con licencia por volumen del producto. Para ejecutar la OCT, escriba en la línea de comandos desde la raíz del punto de instalación de red  `setup.exe /admin` que contiene los archivos de origen de Office. Por ejemplo, utilice lo siguiente:
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
Los administradores usan la OCT para crear un archivo .msp de personalización del programa de instalación y pueden personalizar las siguientes áreas:
  
- **Configuración** Se usa para especificar la ubicación de instalación predeterminada en el nombre de la organización predeterminado y del cliente, los orígenes de instalación de red adicionales, la clave de producto, el contrato de licencia de usuario final, el nivel de visualización, las versiones anteriores de Office que se quitarán, los programas personalizados que se ejecutarán durante la instalación, la configuración de seguridad y las propiedades de instalación.
    
- **Características** Se usa para configurar las opciones de usuario y personalizar la forma en que se instalan las características de Office. Los administradores pueden utilizar la OCT para especificar los valores iniciales predeterminados de la aplicación de Office para los usuarios. Los usuarios pueden modificar la mayoría de las opciones después de la instalación.
    
- **Contenido adicional** Se usa para agregar o quitar archivos, agregar o quitar entradas del Registro y configurar accesos directos.
    
- **Outlook** Se usa para personalizar el perfil predeterminado de Outlook de un usuario, especificar la configuración de Exchange, agregar cuentas, quitar cuentas y exportar la configuración y especificar grupos de envío y recepción.
    
Para obtener información acerca de la OCT, vea [Use the OCT to customize Office 2013](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)). Tenga en cuenta que esta información también se aplica a versiones posteriores de Office.
