---
title: Usar la herramienta de personalización de Office (OCT) en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Resumen: Cómo usar la herramienta de personalización de Office con el cliente de Skype empresarial.'
ms.openlocfilehash: a71ab8947d964dff90510257c4a8b2cbffb3be96
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306205"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Usar la herramienta de personalización de Office (OCT) en Skype empresarial Server
 
**Resumen:** Cómo usar la herramienta de personalización de Office con el cliente de Skype empresarial.
  
La herramienta de personalización de Office (OCT) forma parte del programa de instalación y es la herramienta recomendada para muchas personalizaciones. Al usar la OCT, se personaliza Office y se guardan las personalizaciones en un archivo. MSP de personalización del programa de instalación. El archivo se coloca en la carpeta actualizaciones del punto de instalación de red. Al instalar Office, el programa de instalación busca un archivo de personalización de la configuración en la carpeta actualizaciones y aplica las personalizaciones. La carpeta actualizaciones solo se puede usar para implementar actualizaciones de software durante una instalación inicial de Office.
  
La OCT es parte de la configuración y solo se usa para las versiones con licencia por volumen del producto. Para ejecutar la OCT, escriba `setup.exe /admin` en la línea de comandos de la raíz del punto de instalación de red que contiene los archivos de origen de Office. Por ejemplo, use lo siguiente:
  
 ```
\\server\share\Office15\setup.exe /admin
```
  
Los administradores usan la OCT para crear un archivo. MSP de personalización del programa de instalación y pueden personalizar las siguientes áreas:
  
- **Configuración** Se usa para especificar la ubicación de instalación predeterminada en el cliente y el nombre de la organización predeterminada, otras fuentes de instalación en red, la clave de producto, el contrato de licencia para el usuario final, el nivel de presentación, las versiones anteriores de Office que se deben quitar y los programas personalizados que se ejecutan durante instalación, configuración de seguridad y propiedades de configuración.
    
- **Características** Se usa para configurar las opciones de usuario y personalizar la instalación de las características de Office. Los administradores pueden usar la OCT para especificar los valores iniciales predeterminados de la aplicación de Office para los usuarios. Los usuarios pueden modificar la mayoría de las opciones después de la instalación.
    
- **Contenido adicional** Se usa para agregar o quitar archivos, agregar o quitar entradas del registro y configurar accesos directos.
    
- **Outlook** Se usa para personalizar el perfil predeterminado de Outlook de un usuario, especificar la configuración de Exchange, agregar cuentas, quitar cuentas y exportar configuraciones, y especificar grupos de envío y recepción.
    
Para obtener más información sobre la OCT, consulte [usar la Oct para personalizar Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)). Tenga en cuenta que esta información también se aplica a versiones posteriores de Office.
  

