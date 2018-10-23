---
title: Usar Config.xml para realizar tareas de instalación en Skype para clientes empresariales
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Resumen: cómo usar el archivo Config.xml para especificar instrucciones de instalación adicionales.'
ms.openlocfilehash: dfb6625146261b1bbf22e0f563717899c68beaae
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699561"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Usar Config.xml para realizar tareas de instalación en Skype para clientes empresariales

**Resumen:** cómo usar el archivo Config.xml para especificar instrucciones de instalación adicionales.

Aunque la Herramienta de personalización de Office (OCT) es la principal herramienta de instalación personalizada, los administradores pueden usar el archivo Config.xml para especificar instrucciones de instalación adicionales que no estén disponibles en la OCT. Las personalizaciones que se describen a continuación solo se pueden llevar a cabo mediante el archivo Config.xml:

- Especifique la ruta de acceso del punto de instalación de red.

- Seleccione los productos que desea instalar.

- Configure el registro y la ubicación del archivo de personalización de la instalación y las actualizaciones de software.

- Especifique las opciones de instalación como, por ejemplo, el nombre de usuario.

- Copie el origen de instalación local (LIS) en el equipo del usuario sin instalar Office.

- Agregue o quite idiomas de la instalación.

Se recomienda que utilice el archivo Config.xml para configurar Skype para la instalación silenciosa de negocio. 

De forma predeterminada, el archivo Config.xml que se almacena en la carpeta de producto principal (por ejemplo, \ _producto_. WW) dirige el programa de instalación que instale ese producto. Por ejemplo, el archivo Config.xml en la carpeta siguiente instala Skype para la empresa:

- \\server\share\Skype15\Skype.WW \Config.xml

Los elementos de Config.xml usados con más frecuencia para Skype para la instalación de negocio se enumeran en la siguiente tabla.

**Elementos de Config.xml**


| **Elemento**              | **Descripción**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configuración  <br/>     | Elemento de nivel superior (obligatorio). Contiene el atributo del producto, como Product=Lync (esto funcionará con clientes de Skype Empresarial)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | Especifica cómo se controlan las características específicas del producto durante la instalación. Use los siguientes atributos para impedir la instalación de servicios de conectividad empresarial, que incluye los componentes compartidos que interferirán con Outlook: <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| Pantalla  <br/>           | El nivel de interfaz de usuario que el programa de instalación muestra al usuario. Los atributos típicos incluyen los siguientes: <br/>  CompletionNotice = "Yes"                                                                                                                                                                                |
| Registro  <br/>           | Opciones para el tipo de registro que realiza el programa de instalación. Los atributos típicos incluyen los siguientes: <br/>  Tipo = "Off"                                                                                                                                                                                       |
| Configuración  <br/>           | Especifica los valores de propiedades de Windows Installer. Los atributos típicos incluyen los siguientes:<br/>  Setting Id = " *nombre*" (el nombre de la propiedad de Windows Installer)  <br/>  Valor = " *valor*" (el valor para asignar a la propiedad)  <br/>                                                             |
| DistributionPoint  <br/> | La ruta de acceso completa del punto de instalación de red desde la que se ejecuta la instalación. Incluye el atributo de ubicación:<br/>  Ubicación = " *ruta de acceso*"  <br/>                                                                                                                                     |

En el ejemplo siguiente se muestra un archivo Config.xml para una instalación silenciosa típica de la Skype para clientes empresariales. 

```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Obtener información detallada acerca de cómo utilizar el archivo Config.xml para realizar tareas de instalación y mantenimiento de Office está disponible en [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).

## <a name="to-customize-the-configxml-file"></a>Para personalizar el archivo Config.xml

1. Abra el archivo Config.xml usando una herramienta de edición de texto como el Bloc de notas.

2. Localice las líneas que contienen los elementos que desee cambiar.

3. Modifique la entrada de elemento con las opciones silenciosas que desea usar. Asegúrese de que quita los delimitadores de comentarios, "\<!--" y "--\>". Por ejemplo, utilice la sintaxis siguiente:

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Guarde el archivo Config.xml.


