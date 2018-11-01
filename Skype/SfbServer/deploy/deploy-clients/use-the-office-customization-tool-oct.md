---
title: Use la herramienta de personalización de Office (OCT) en Skype para Business Server
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Resumen: Cómo usar la herramienta de personalización de Office con el Skype para clientes empresariales.'
ms.openlocfilehash: 6050a9e9c36fa62aff16994469e63a9689ab5958
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838668"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Use la herramienta de personalización de Office (OCT) en Skype para Business Server
 
**Resumen:** Cómo usar la herramienta de personalización de Office con el Skype para clientes empresariales.
  
La herramienta de personalización de Office (OCT) es parte del programa de instalación y es la herramienta recomendada para muchas personalizaciones. Mediante el uso de la herramienta OCT, personalización de Office y guardar las personalizaciones en un archivo .msp de personalización. Coloque el archivo en la carpeta actualizaciones del punto de instalación de red. Al instalar Office, el programa de instalación busca un archivo de personalización del programa de instalación en la carpeta actualizaciones y aplica las personalizaciones. La carpeta de actualizaciones se puede usar solo para implementar actualizaciones de software durante la instalación inicial de Office.
  
La herramienta OCT forma parte del programa de instalación y sólo se utiliza para las versiones de licencia por volumen del producto. Ejecute la herramienta OCT escribiendo `setup.exe /admin` en la línea de comandos desde la raíz del punto de instalación de red que contiene la oficina de los archivos de origen. Por ejemplo, use lo siguiente:
  
 ```
\\server\share\Office15\setup.exe /admin
```
  
Los administradores usan la herramienta OCT para crear un archivo .msp de personalización y puede personalizar las siguientes áreas:
  
- **Programa de instalación** Se utiliza para especificar la ubicación de instalación predeterminada en el nombre de la organización de cliente y de forma predeterminada, los orígenes de instalación de red adicionales, clave de producto, contrato de licencia para el usuario final, mostrar el nivel de versiones anteriores de Office para quitar programas personalizados que se ejecutan durante instalación, configuración de seguridad y las propiedades del programa de instalación.
    
- **Características** Se usa para establecer la configuración de usuario y para personalizar el modo en que se instalan las características de Office. Los administradores pueden usar la OCT para especificar los valores iniciales predeterminados de la aplicación de Office para los usuarios. Los usuarios pueden modificar la mayoría de las opciones después de la instalación.
    
- **Contenido adicional** Se usa para agregar o quitar archivos, agregar o quitar entradas del registro y configurar accesos directos.
    
- **Outlook** Usar para personalizar el perfil predeterminado de Outlook de un usuario, especificar la configuración de Exchange, agregar cuentas, quitar cuentas y exportar la configuración de y especificar grupos de envío o recepción.
    
Para obtener información acerca de la herramienta OCT, vea [utilizar la herramienta OCT para personalizar Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)). Tenga en cuenta que esta información también se aplica a las versiones posteriores de Office.
  

