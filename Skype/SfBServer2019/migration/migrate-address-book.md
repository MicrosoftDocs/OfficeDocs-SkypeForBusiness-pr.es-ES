---
title: Migrar la libreta de direcciones
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'En general, la libreta de direcciones se migra junto con el resto de la topología. Sin embargo, es posible que tenga que realizar algunos pasos posteriores a la migración si ha personalizado lo siguiente en su entorno heredado:'
ms.openlocfilehash: 8c8e66a8182890ee6e3673769ddc620bb04404c6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990105"
---
# <a name="migrate-address-book"></a>Migrar la libreta de direcciones

En general, la libreta de direcciones se migra junto con el resto de la topología. Sin embargo, es posible que tenga que realizar algunos pasos posteriores a la migración si ha personalizado lo siguiente en su entorno heredado: 

- Personalizar las reglas de normalización de la libreta de direcciones.

- Cambió el valor predeterminado del parámetro **UseNormalizationRules** a false. 


 **Reglas de normalización de libreta de direcciones**

Si ha personalizado las reglas de normalización de la libreta de direcciones en el entorno heredado, debe migrar las reglas personalizadas a su grupo piloto. Si no ha personalizado las reglas de normalización de la libreta de direcciones, no tiene nada que migrar para el servicio de libreta de direcciones. Las reglas de normalización predeterminadas para Skype empresarial Server 2019 son las mismas que las reglas predeterminadas para la instalación heredada. Siga el procedimiento más adelante en esta sección para migrar reglas de normalización personalizadas.

> [!NOTE]
> Si su organización usa el control remoto de llamadas y ha personalizado las reglas de normalización de la libreta de direcciones, debe realizar el procedimiento de este tema antes de poder usar el control remoto de llamadas. El procedimiento requiere ser miembro del grupo RTCUniversalServerAdmins o derechos equivalentes. 

 **UseNormalizationRules establecido en falso**

Si establece el valor de **UseNormalizationRules** en false para que los usuarios puedan usar números de teléfono a medida que se definen en servicios de dominio de Active Directory sin tener Skype empresarial Server 2019 aplicar reglas de normalización, debe configurar los parámetros **UseNormalizationRules** y **IgnoreGenericRules** en true. Siga el procedimiento más adelante en esta sección para establecer estos parámetros en true. 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Para migrar reglas de normalización personalizadas de la libreta de direcciones

1. Busque el archivo Company_Phone_Number_Normalization_Rules. txt en la raíz de la carpeta compartida de la libreta de direcciones y cópielo en la raíz de la carpeta compartida de la libreta de direcciones en el grupo piloto de Skype empresarial Server 2019.

    > [!NOTE]
    > Las reglas de normalización de libreta de direcciones de muestra se han instalado en el directorio de archivos de ABS web Component. La ruta de acceso es **$installedDriveLetter: \Archivos de Programa\microsoft Skype for Business Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt**. Este archivo se puede copiar y cambiar de nombre como **Company_Phone_Number_Normalization_Rules. txt** al directorio raíz de la carpeta compartida de la libreta de direcciones. Por ejemplo, la libreta de direcciones compartida en **$serverX**, la ruta de acceso será similar a: ** \\$serverX \SkypeForBusiness-FileShare\2-webservices-1\ABFiles**. 

2. Use un editor de texto, como el Bloc de notas, para abrir el archivo Company_Phone_Number_Normalization_Rules. txt.

3. Ciertos tipos de entradas no funcionarán correctamente en Skype empresarial Server 2019. Busque en el archivo los tipos de entradas que se describen en este paso, edítelo según sea necesario y guarde los cambios en la carpeta compartida de la libreta de direcciones del grupo piloto.

    Las cadenas que incluyen el espacio en blanco o la puntuación obligatorios producen errores en las reglas de normalización, ya que estos caracteres se eliminan de la cadena introducida en las reglas de normalización. Si tiene cadenas que incluyen el espacio en blanco o la puntuación necesarios, debe modificar las cadenas. Por ejemplo, la siguiente cadena haría que la regla de normalra fallara:

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    La cadena siguiente no provocará errores en la regla de normalización:

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Para establecer UseNormalizationRules y IgnoreGenericRules en true

1. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **consola de administración de Skype empresarial Server**.

2. Siga uno de estos pasos:

   - Si su implementación solo incluye Skype empresarial Server 2019, ejecute el siguiente cmdlet en el nivel global para cambiar los valores de **UseNormalizationRules** y **IgnoreGenericRules** a verdadero: 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - Si su implementación incluye una combinación de Skype empresarial Server 2019 y una instalación heredada, ejecute el siguiente cmdlet y asígnelo a cada grupo de Skype empresarial Server 2019 en la topología:

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. Espere a que se produzca la replicación del almacén central de administración en todos los grupos.

4. Modifique el archivo de reglas de normalización de teléfono, "Company_Phone_Number_Normalization_Rules. txt", para que su implementación borre el contenido. El archivo se encuentra en el recurso compartido de archivos de cada grupo de servidores de Skype empresarial 2019. Si el archivo no está presente, cree un archivo vacío denominado "Company_Phone_Number_Normalization_Rules. txt".

5. Espere unos minutos hasta que todos los grupos de servidores front-end lean los nuevos archivos.

6. Ejecute el siguiente cmdlet en cada grupo de servidores de Skype empresarial 2019 de su implementación:

   ```PowerShell
   Update-CsAddressBook
   ```


