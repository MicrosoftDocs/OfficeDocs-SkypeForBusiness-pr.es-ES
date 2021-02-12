---
title: Usar Config.xml para realizar tareas de instalación en clientes de Skype Empresarial
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Resumen: cómo usar el archivo Config.xml para especificar instrucciones de instalación adicionales.'
ms.openlocfilehash: 1b8aeeb16e061e7816e475f01c9cd9a9146306ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825190"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Usar Config.xml para realizar tareas de instalación en clientes de Skype Empresarial

**Resumen:** Cómo usar el archivo Config.xml para especificar instrucciones de instalación adicionales.

Aunque la Herramienta de personalización de Office (OCT) es la principal herramienta de instalación personalizada, los administradores pueden usar el archivo Config.xml para especificar instrucciones de instalación adicionales que no estén disponibles en la OCT. Las personalizaciones que se describen a continuación solo se pueden llevar a cabo mediante el archivo Config.xml:

- Especifique la ruta de acceso del punto de instalación de red.

- Seleccione los productos que desea instalar.

- Configure el registro y la ubicación del archivo de personalización de la instalación y las actualizaciones de software.

- Especifique las opciones de instalación como, por ejemplo, el nombre de usuario.

- Copie el origen de instalación local (LIS) en el equipo del usuario sin instalar Office.

- Agregar o quitar idiomas de la instalación.

Le recomendamos que use el archivo Config.xml para configurar la instalación silenciosa de Skype Empresarial. 

De forma predeterminada, Config.xml archivo que se almacena en la carpeta principal del producto (por ejemplo, \ _product_. WW) le dirige al programa de instalación para que instale ese producto. Por ejemplo, el archivo Config.xml en la carpeta siguiente instala Skype Empresarial:

- \\server\share\Skype15\Skype.WW \Config.xml

En la Config.xml se enumeran los elementos que se usan con más frecuencia para la instalación de Skype Empresarial.

**Elementos de Config.xml**


| **Elemento**              | **Descripción**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configuración  <br/>     | Elemento de nivel superior (necesario). Contiene el atributo Product, por ejemplo: Product=Lync (esto funcionará para clientes de Skype Empresarial)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | Especifica cómo las características específicas del producto se controlan durante la instalación. Use los siguientes atributos para evitar la instalación de Servicios de conectividad empresarial, que incluye componentes compartidos que interfieren con Outlook: <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| Visualización  <br/>           | El nivel de interfaz de usuario que el programa de instalación muestra al usuario. Los atributos típicos incluyen los siguientes: <br/>  CompletionNotice="Yes"                                                                                                                                                                                |
| Registro  <br/>           | Opciones para el tipo de registro que realiza el programa de instalación. Los atributos típicos incluyen los siguientes: <br/>  Type ="Off"                                                                                                                                                                                       |
| Setting  <br/>           | Especifica los valores de propiedades de Windows Installer. Los atributos típicos incluyen los siguientes:<br/>  Setting Id=" *name*" (el nombre de la propiedad de Windows Installer)  <br/>  Valor=" *valor*" (el valor que se asignará a la propiedad)  <br/>                                                             |
| DistributionPoint  <br/> | La ruta de acceso completa del punto de instalación de red desde la que se ejecuta la instalación. Incluye el atributo de ubicación:<br/>  Location=" *path*"  <br/>                                                                                                                                     |

En el ejemplo siguiente se muestra un Config.xml archivo para una instalación silenciosa típica del cliente de Skype Empresarial. 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Encontrará información detallada sobre cómo usar el Config.xml para realizar tareas de instalación y mantenimiento de Office en [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514) .

## <a name="to-customize-the-configxml-file"></a>Para personalizar el archivo Config.xml

1. Abra el archivo Config.xml usando una herramienta de edición de texto como el Bloc de notas.

2. Localice las líneas que contienen los elementos que desee cambiar.

3. Modifique la entrada de elemento con las opciones silenciosas que desea usar. Asegúrese de quitar los delimitadores de comentarios, " \<!--" and "--\> ". Por ejemplo, utilice la sintaxis siguiente:

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Guarde el archivo Config.xml.


