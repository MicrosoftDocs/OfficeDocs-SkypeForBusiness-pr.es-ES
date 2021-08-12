---
title: Use la herramienta Office personalización (OCT) de Skype Empresarial Server
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
description: 'Resumen: Cómo usar la herramienta de personalización Office con el Skype Empresarial cliente.'
ms.openlocfilehash: 383db7b623790153114740c4d245823c38ec63c5881842c281e6c10f7834a450
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294927"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Use la herramienta Office personalización (OCT) de Skype Empresarial Server
 
**Resumen:** Cómo usar la herramienta de personalización Office con el Skype Empresarial cliente.
  
La Office personalización (OCT) forma parte del programa de instalación y es la herramienta recomendada para muchas personalizaciones. Al usar la OCT, puede personalizar Office y guardar las personalizaciones en un archivo .msp de personalización del programa de instalación. El archivo se coloca en la carpeta Actualizaciones del punto de instalación en red. Al instalar Office, el programa de instalación busca un archivo de personalización del programa de instalación en la carpeta Actualizaciones y aplica las personalizaciones. La carpeta Actualizaciones solo se puede usar para implementar actualizaciones de software durante una instalación inicial de Office.
  
La OCT forma parte de la configuración y solo se usa para las versiones con licencia por volumen del producto. Para ejecutar la OCT, escriba en la línea de comandos desde la raíz del punto de instalación de red que contiene los `setup.exe /admin` Office de origen. Por ejemplo, utilice lo siguiente:
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
Los administradores usan la OCT para crear un archivo .msp de personalización del programa de instalación y pueden personalizar las siguientes áreas:
  
- **Configuración** Se usa para especificar la ubicación de instalación predeterminada en el nombre del cliente y la organización predeterminada, orígenes de instalación de red adicionales, clave de producto, contrato de licencia de usuario final, nivel de presentación, versiones anteriores de Office para quitar, programas personalizados que se ejecutarán durante la instalación, configuración de seguridad y propiedades de instalación.
    
- **Características** Se usa para configurar la configuración del usuario y personalizar la Office se instalan las características. Los administradores pueden utilizar la OCT para especificar los valores iniciales predeterminados de la aplicación de Office para los usuarios. Los usuarios pueden modificar la mayoría de las opciones después de la instalación.
    
- **Contenido adicional** Se usa para agregar o quitar archivos, agregar o quitar entradas del Registro y configurar accesos directos.
    
- **Outlook** Se usa para personalizar el perfil de Outlook predeterminado de un usuario, especificar la configuración de Exchange, agregar cuentas, quitar cuentas y exportar la configuración y especificar grupos de envío y recepción.
    
Para obtener información acerca de la OCT, vea [Use the OCT to customize Office 2013](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)). Tenga en cuenta que esta información también se aplica a versiones posteriores de Office.
