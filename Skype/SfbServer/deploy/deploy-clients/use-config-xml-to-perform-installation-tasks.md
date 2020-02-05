---
title: Usar config. XML para realizar tareas de instalación en clientes de Skype empresarial
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: a935e3623e99324eb24caef4e7e232d2311c5cfb
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768653"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Usar config. XML para realizar tareas de instalación en clientes de Skype empresarial

**Resumen:** cómo usar el archivo Config.xml para especificar instrucciones de instalación adicionales.

Aunque la Herramienta de personalización de Office (OCT) es la principal herramienta de instalación personalizada, los administradores pueden usar el archivo Config.xml para especificar instrucciones de instalación adicionales que no estén disponibles en la OCT. Las personalizaciones que se describen a continuación solo se pueden llevar a cabo mediante el archivo Config.xml:

- Especifique la ruta de acceso del punto de instalación de red.

- Seleccione los productos que desea instalar.

- Configure el registro y la ubicación del archivo de personalización de la instalación y las actualizaciones de software.

- Especifique las opciones de instalación como, por ejemplo, el nombre de usuario.

- Copie el origen de instalación local (LIS) en el equipo del usuario sin instalar Office.

- Agregue o quite idiomas de la instalación.

Le recomendamos que use el archivo config. XML para configurar la instalación silenciosa de Skype empresarial. 

De forma predeterminada, el archivo config. XML que se almacena en la carpeta de producto principal (por ejemplo, \ _Product_. WW) indica al programa de instalación que instale ese producto. Por ejemplo, el archivo config. XML de la siguiente carpeta instala Skype empresarial:

- \\server\share\Skype15\Skype.WW \Config.xml

Los elementos de config. XML más usados en la instalación de Skype empresarial se muestran en la tabla siguiente.

**Elementos de Config.xml**


| **Elemento**              | **Descripción**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configuración  <br/>     | Elemento de nivel superior (obligatorio). Contiene el atributo del producto, como Product=Lync (esto funcionará con clientes de Skype Empresarial)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | Especifica cómo se controlan las características específicas del producto durante la instalación. Use los siguientes atributos para impedir la instalación de los servicios de conectividad empresarial, que incluyen componentes compartidos que interfieren con Outlook: <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| Pantalla  <br/>           | El nivel de interfaz de usuario que el programa de instalación muestra al usuario. Los atributos típicos incluyen los siguientes: <br/>  CompletionNotice = "sí"                                                                                                                                                                                |
| Registro  <br/>           | Opciones para el tipo de registro que realiza el programa de instalación. Los atributos típicos incluyen los siguientes: <br/>  Escriba = "OFF"                                                                                                                                                                                       |
| Configuración  <br/>           | Especifica los valores de propiedades de Windows Installer. Los atributos típicos incluyen los siguientes:<br/>  Setting ID = " *Name*" (el nombre de la propiedad de Windows Installer)  <br/>  Value = " *Value*" (el valor que se asignará a la propiedad)  <br/>                                                             |
| DistributionPoint  <br/> | La ruta de acceso completa del punto de instalación de red desde la que se ejecuta la instalación. Incluye el atributo de ubicación:<br/>  Location = " *rutaDeAcceso*"  <br/>                                                                                                                                     |

En el ejemplo siguiente se muestra un archivo config. XML para una instalación normal silenciosa del cliente de Skype empresarial. 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Encontrará información detallada sobre cómo usar el archivo config. XML para realizar tareas de instalación y mantenimiento de [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514)Office en.

## <a name="to-customize-the-configxml-file"></a>Para personalizar el archivo Config.xml

1. Abra el archivo Config.xml usando una herramienta de edición de texto como el Bloc de notas.

2. Localice las líneas que contienen los elementos que desee cambiar.

3. Modifique la entrada de elemento con las opciones silenciosas que desea usar. Asegúrese de quitar los delimitadores de comentarios, "\<!--" y "--\>". Por ejemplo, utilice la sintaxis siguiente:

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Guarde el archivo Config.xml.


