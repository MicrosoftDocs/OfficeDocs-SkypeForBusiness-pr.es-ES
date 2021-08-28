---
title: Usar Config.xml para realizar tareas de instalación en Skype Empresarial cliente
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Summary: How to use the Config.xml file to specify additional installation instructions.'
ms.openlocfilehash: f79dcc1d31fdd862ca8705552d7894dcdd90fcd7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620496"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Usar Config.xml para realizar tareas de instalación en Skype Empresarial cliente

**Resumen:** Cómo usar el archivo Config.xml para especificar instrucciones de instalación adicionales.

Aunque la Herramienta de personalización de Office (OCT) es la principal herramienta de instalación personalizada, los administradores pueden usar el archivo Config.xml para especificar instrucciones de instalación adicionales que no estén disponibles en la OCT. Las personalizaciones que se describen a continuación solo se pueden llevar a cabo mediante el archivo Config.xml:

- Especifique la ruta de acceso del punto de instalación de red.

- Seleccione los productos que desea instalar.

- Configure el registro y la ubicación del archivo de personalización de la instalación y las actualizaciones de software.

- Especifique las opciones de instalación como, por ejemplo, el nombre de usuario.

- Copie el origen de instalación local (LIS) en el equipo del usuario sin instalar Office.

- Agregar o quitar idiomas de la instalación.

Se recomienda usar el archivo Config.xml para configurar la Skype Empresarial silenciosa. 

De forma predeterminada, el Config.xml que se almacena en la carpeta principal del producto (por ejemplo, \ _product_. WW) dirige al programa de instalación a instalar ese producto. Por ejemplo, el archivo Config.xml en la siguiente carpeta se instala Skype Empresarial:

- \\server\share\Skype15\Skype. WW \Config.xml

Los Config.xml más usados para la Skype Empresarial se enumeran en la tabla siguiente.

**Elementos de Config.xml**


| **Elemento**              | **Descripción**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configuración  <br/>     | Elemento de nivel superior (necesario). Contiene el atributo Product, por ejemplo: Product=Lync (Esto funcionará para Skype Empresarial clientes)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | Especifica cómo las características específicas del producto se controlan durante la instalación. Use los siguientes atributos para impedir la instalación de Servicios de conectividad empresarial, que incluye componentes compartidos que interfieren con Outlook: <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| Pantalla  <br/>           | El nivel de interfaz de usuario que el programa de instalación muestra al usuario. Los atributos típicos incluyen los siguientes: <br/>  CompletionNotice="Yes"                                                                                                                                                                                |
| Registro  <br/>           | Opciones para el tipo de registro que realiza el programa de instalación. Los atributos típicos incluyen los siguientes: <br/>  Tipo ="Off"                                                                                                                                                                                       |
| Valor  <br/>           | Especifica los valores de propiedades de Windows Installer. Los atributos típicos incluyen los siguientes:<br/>  Setting Id=" *name*" (el nombre de la propiedad Windows Installer)  <br/>  Valor=" *valor*" (el valor que se debe asignar a la propiedad)  <br/>                                                             |
| DistributionPoint  <br/> | La ruta de acceso completa del punto de instalación de red desde la que se ejecuta la instalación. Incluye el atributo de ubicación:<br/>  Ruta de *acceso* Location="  <br/>                                                                                                                                     |

En el ejemplo siguiente se muestra un Config.xml archivo para una instalación silenciosa típica del Skype Empresarial cliente. 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Encontrará información detallada sobre cómo usar el archivo Config.xml para realizar Office tareas de instalación y mantenimiento en [https://go.microsoft.com/fwlink/p/?linkid=267514](/previous-versions/office/office-2013-resource-kit/cc179195(v=office.15)) .

## <a name="to-customize-the-configxml-file"></a>Para personalizar el archivo Config.xml

1. Abra el archivo Config.xml usando una herramienta de edición de texto como el Bloc de notas.

2. Localice las líneas que contienen los elementos que desee cambiar.

3. Modifique la entrada de elemento con las opciones silenciosas que desea usar. Asegúrese de quitar los delimitadores de comentario, " \<!--" and "--\> ". Por ejemplo, utilice la sintaxis siguiente:

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Guarde el archivo Config.xml.