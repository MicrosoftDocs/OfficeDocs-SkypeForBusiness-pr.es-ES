---
title: Migrar la libreta de direcciones
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'En general, la libreta de direcciones se migra junto con el resto de la topología. Sin embargo, es posible que necesite realizar algunos pasos posteriores a la migración si ha personalizado lo siguiente en el entorno heredado:'
ms.openlocfilehash: 728ae97270cd8451178c6ef962f05e0351118119
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238427"
---
# <a name="migrate-address-book"></a>Migrar la libreta de direcciones

En general, la libreta de direcciones se migra junto con el resto de la topología. Sin embargo, es posible que necesite realizar algunos pasos posteriores a la migración si ha personalizado lo siguiente en el entorno heredado: 

- Puede personalizar las reglas de normalización de la libreta de direcciones.

- Cambiar el valor predeterminado para el parámetro **UseNormalizationRules** en False. 


 **Reglas de normalización de la libreta de direcciones**

Si ha personalizado las reglas de normalización de la libreta de direcciones en el entorno heredado, debe migrar las reglas personalizadas a su grupo piloto. Si no personalizó las reglas de normalización de la libreta de direcciones, deberá nothing para migrar para el servicio de libreta de direcciones. Las reglas de normalización de forma predeterminada para Skype para Business Server 2019 son los mismos que las reglas predeterminadas para la instalación heredada. Siga el procedimiento más adelante en esta sección para migrar reglas de normalización personalizadas.

> [!NOTE]
> Si su organización utiliza control remoto de llamadas y ha personalizado las reglas de normalización de la libreta de direcciones, debe realizar el procedimiento de este tema para poder usar el control remoto de llamadas. El procedimiento, es necesario pertenecer al grupo RTCUniversalServerAdmins o derechos equivalentes. 

 **UseNormalizationRules en False**

Si establece el valor de **UseNormalizationRules** en False para que los usuarios pueden usar los números de teléfono tal y como están definidos en los servicios de dominio de Active Directory sin necesidad de Skype para Business Server 2019 se aplican las reglas de normalización, debe establecer el ** UseNormalizationRules** y los parámetros de **IgnoreGenericRules** en True. Siga el procedimiento descrito más adelante en esta sección para establecer estos parámetros en True. 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Para migrar la libreta de direcciones personalizadas de reglas de normalización

1. Busque el archivo Company_Phone_Number_Normalization_Rules.txt en la raíz de la carpeta compartida de la libreta de direcciones y cópielo a la raíz de la carpeta compartida de la libreta de direcciones en su Skype para el grupo piloto Business Server 2019.

    > [!NOTE]
    > Las reglas de normalización de ejemplo Libreta de direcciones se han instalado en el directorio de archivos de componente Web ABS. Es la ruta de acceso **$installedDriveLetter: \Program Skype para Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**. Este archivo se puede copiar a cambiar el nombre como **Company_Phone_Number_Normalization_Rules.txt** al directorio raíz de la carpeta Libreta de direcciones compartida. Por ejemplo, la libreta de direcciones compartida en **$serverX**, la ruta de acceso será similar a: ** \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**. 

2. Use un editor de texto, como el Bloc de notas para abrir el archivo Company_Phone_Number_Normalization_Rules.txt.

3. Ciertos tipos de entradas no funcionarán correctamente en Skype para Business Server 2019. Examine el archivo para los tipos de entradas descritos en este paso, editarlos según sea necesario y guardar los cambios en la carpeta compartida de la libreta de direcciones en el grupo piloto.

    Cadenas que incluyen requiere espacio en blanco o signos de puntuación causa reglas de normalización se lleve a cabo debido a que estos caracteres se eliminan fuera de la cadena que es la entrada a las reglas de normalización. Si dispone de las cadenas que incluyen el espacio en blanco obligatorio ni signos de puntuación, debe modificar las cadenas. Por ejemplo, la siguiente cadena hará que la regla de normalización se lleve a cabo:

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    La siguiente cadena no hará que la regla de normalización se lleve a cabo:

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Para establecer UseNormalizationRules e IgnoreGenericRules en true

1. Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Microsoft Skype para Business Server 2019**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.

2. Siga uno de estos pasos:

   - Si la implementación incluye solo Skype para Business Server 2019, ejecute el siguiente cmdlet en el nivel global para cambiar los valores de **UseNormalizationRules** e **IgnoreGenericRules** a True: 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - Si la implementación incluye una combinación de Skype para Business Server 2019 y una instalación heredada, ejecute el siguiente cmdlet y asígnelo a cada Skype para Business Server 2019 grupo de servidores en la topología:

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. Espere a que se producen en todos los grupos de la replicación de almacén de Administración Central.

4. Modifique el archivo de reglas de normalización de teléfono, "Company_Phone_Number_Normalization_Rules.txt", para la implementación borrar el contenido. El archivo está en el recurso compartido de archivos de cada Skype para el grupo de servidores de Business Server 2019. Si el archivo no está presente, a continuación, cree un archivo vacío denominado "Company_Phone_Number_Normalization_Rules.txt".

5. Espere varios minutos para todos los grupos de servidores Front-End leer los nuevos archivos.

6. Ejecute el siguiente cmdlet en cada Skype para grupo de negocio Server 2019 en su implementación:

   ```
   Update-CsAddressBook
   ```


