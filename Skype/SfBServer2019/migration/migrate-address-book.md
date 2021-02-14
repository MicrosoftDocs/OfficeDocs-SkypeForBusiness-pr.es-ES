---
title: Migrar la libreta de direcciones
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'En general, la libreta de direcciones se migra junto con el resto de la topología. Sin embargo, es posible que deba realizar algunos pasos posteriores a la migración si personalizó lo siguiente en su entorno heredado:'
ms.openlocfilehash: 6d2ccf0d38814d149495518a71f888f0c2999d24
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752842"
---
# <a name="migrate-address-book"></a>Migrar la libreta de direcciones

En general, la libreta de direcciones se migra junto con el resto de la topología. Sin embargo, es posible que deba realizar algunos pasos posteriores a la migración si personalizó lo siguiente en su entorno heredado: 

- Personalizó las reglas de normalización de la libreta de direcciones.

- Modificó el valor predeterminado del parámetro **UseNormalizationRules** a False. 


 **Reglas de normalización de la Libreta de direcciones**

Si personalizó las reglas de normalización de la libreta de direcciones en su entorno heredado, debe migrar las reglas personalizadas al grupo piloto. Si no ha personalizado las reglas de normalización de la Libreta de direcciones, no tendrá nada que migrar al servicio de la Libreta de direcciones. Las reglas de normalización predeterminadas para Skype Empresarial Server 2019 son las mismas que las reglas predeterminadas para la instalación heredada. Siga el procedimiento que se describe más adelante en esta sección para migrar reglas de normalización personalizadas.

> [!NOTE]
> Si su organización usa el control remoto de llamadas y personalizó las reglas de normalización de la libreta de direcciones, deberá llevar a cabo el procedimiento que se describe en este tema para poder usar el control remoto de llamadas. El procedimiento requiere pertenecer al grupo RTCUniversalServerAdmins o contar con derechos equivalentes. 

 **Definición de UseNormalizationRules en False**

Si establece el valor de **UseNormalizationRules** en False para que los usuarios puedan usar números de teléfono tal como se definen en los Servicios de dominio de Active Directory sin que Skype Empresarial Server 2019 aplique reglas de normalización, debe establecer los parámetros **UseNormalizationRules** e **IgnoreGenericRules** en True. Siga el procedimiento que se describe más adelante en esta sección para establecer estos parámetros en True. 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Para migrar reglas de normalización personalizadas de la libreta de direcciones

1. Busque el Company_Phone_Number_Normalization_Rules.txt en la raíz de la carpeta compartida de la libreta de direcciones y cópielo en la raíz de la carpeta compartida de la libreta de direcciones en su grupo piloto de Skype Empresarial Server 2019.

    > [!NOTE]
    > Las reglas de normalización de la libreta de direcciones de muestra se instalaron en el directorio de archivos de componentes web de ABS. La ruta de acceso **es $installedDriveLetter:\Archivos de programa\Microsoft Skype Empresarial Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**. Este archivo se puede copiar y cambiar de nombre como **Company_Phone_Number_Normalization_Rules.txt** al directorio raíz de la carpeta compartida de la libreta de direcciones. Por ejemplo, la libreta de direcciones compartida en **$serverX**, la ruta de acceso será similar a: **\\ $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**. 

2. Use un editor de texto (como el Bloc de notas) para abrir el archivo Company_Phone_Number_Normalization_Rules.txt.

3. Determinados tipos de entradas no funcionarán correctamente en Skype Empresarial Server 2019. Busque en el archivo los tipos de entradas que se describen en este paso, modifíquelos como sea necesario y guarde los cambios en la carpeta compartida de la libreta de direcciones de su grupo piloto.

    Las cadenas que contienen puntuación o espacios en blanco necesarios provocan errores en las reglas de normalización, ya que estos caracteres se quitan de la cadena que se incluye en las reglas de normalización. Si tiene cadenas que incluyen puntuación o espacios en blanco necesarios, deberá modificarlas. Por ejemplo, la siguiente cadena generará un error en la regla de normalización:

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    La siguiente cadena no provocará errores en la regla de normalización:

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Para establecer UseNormalizationRules e IgnoreGenericRules en True

1. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en **Microsoft Skype Empresarial Server 2019** y, a continuación, en Shell de administración de Skype Empresarial **Server.**

2. Realice una de las acciones siguientes:

   - Si la implementación incluye solo Skype Empresarial Server 2019, ejecute el siguiente cmdlet en el nivel global para cambiar los valores de **UseNormalizationRules** e **IgnoreGenericRules** a True: 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - Si la implementación incluye una combinación de Skype Empresarial Server 2019 y una instalación heredada, ejecute el siguiente cmdlet y asígnelo a cada grupo de Skype Empresarial Server 2019 de la topología:

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. Espere a que se produzca la replicación del almacén de administración central en todos los grupos.

4. Modifique el archivo de reglas de normalización del teléfono, "Company_Phone_Number_Normalization_Rules.txt", de su implementación para borrar el contenido. El archivo se encuentra en el recurso compartido de archivos de cada grupo de Skype Empresarial Server 2019. Si no encuentra el archivo, cree un archivo vacío con el nombre "Company_Phone_Number_Normalization_Rules.txt".

5. Espere varios minutos hasta que todos los grupos de servidores front-end lean los nuevos archivos.

6. Ejecute el siguiente cmdlet en cada grupo de Skype Empresarial Server 2019 de su implementación:

   ```PowerShell
   Update-CsAddressBook
   ```


