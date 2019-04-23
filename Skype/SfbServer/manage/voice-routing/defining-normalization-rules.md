---
title: Definición de reglas de normalización en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype para las reglas de normalización de Business Server usar expresiones regulares de .NET Framework para convertir los números de teléfono marcado al formato E.164; en otras palabras, reglas de normalización toman el número de teléfono marcado por un usuario y conversión a ese número en el formato usado internamente por Skype para Business Server. Cada plan de marcado debe tener asignadas una o más reglas de normalización.
ms.openlocfilehash: a1157e9cf435fdd655e9d1772294fa3f57acf3f4
ms.sourcegitcommit: 920a7dbdc2a0ede94d0a4bd573c01a1ccd838b7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "31993518"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Definición de reglas de normalización en Skype para Business Server

Skype para las reglas de normalización de Business Server usar expresiones regulares de .NET Framework para convertir los números de teléfono marcado al formato E.164; en otras palabras, reglas de normalización toman el número de teléfono marcado por un usuario y conversión a ese número en el formato usado internamente por Skype para Business Server. Cada plan de marcado debe tener asignadas una o más reglas de normalización.

Para obtener información detallada acerca de las reglas de normalización, vea [los planes de marcado y reglas de normalización](https://technet.microsoft.com/en-us/library/gg413082(v=ocs.15).aspx).

Para obtener información detallada sobre cómo escribir expresiones regulares, vea [Expresiones regulares de .NET Framework](http://go.microsoft.com/fwlink/p/?linkId=140927).

Puede usar cualquiera de los siguientes métodos para definir o editar una regla de normalización:
- [Use la herramienta de **creación de una regla de normalización** ](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) para especificar valores para los dígitos, longitud, dígitos para quitar y dígitos para agregar y, a continuación, permiten Skype para el Panel de Control de servidor empresarial generar la regla de traducción y el patrón de coincidencia correspondiente inicial Para tí.
- [Escribir manualmente las expresiones regulares](#create-or-modify-a-normalization-rule-manually) para definir la regla de coincidencia de patrón y traducción. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Crear o modificar una regla de normalización mediante generar una regla de normalización

Complete los siguientes pasos si desea crear o modificar una regla de normalización en Skype para el Panel de Control de servidor empresarial. 

**Para definir una regla mediante generar una regla de normalización**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener información detallada, vea [delegar permisos de instalación](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de Control. Para obtener información detallada sobre los distintos métodos que puede usar para iniciar el Skype para el Panel de Control, consulte [Install and open herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. (Opcional) Siga los pasos de [crear un plan de marcado](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan) a través de paso 11 o [modificar un plan de marcado](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan) hasta el paso 10. 
4. En **Nueva regla de normalización** o **Editar regla de normalización**, escriba un nombre que describa el patrón numérico que se normalizará en **Nombre** (por ejemplo, **5DigitExtension**).
5. (Opcional) En **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").
6. En **Generar regla de normalización**, escriba valores en los siguientes campos:
    - **Dígitos iniciales**: (opcional) Especifique los dígitos a la izquierda del marcan los números que desea que coincida el patrón. Por ejemplo, escriba **425** si desea que el patrón coincida con los números marcados que empiecen por 425.
    - **Longitud**: especifique el número de dígitos en la coincidencia de patrón y seleccione si desea que el patrón debe coincidir exactamente con este valor de longitud, coincidencia marcado los números que tienen al menos esta longitud o coincidencia de los números de cualquier longitud marcados con.
    - **Dígitos a quitar**: (opcional) Especifique el número de dígitos que se quitará de los números marcados iniciales que desea que coincida el patrón.
    - **Dígitos a agregar**: (opcional) Especifique dígitos que se agregará a marcar números que desean que coincida el patrón.
    
    Los valores que introduzca en estos campos se reflejarán en **Patrón con el que coincidir** y **Regla de conversión**. Por ejemplo, si deja en blanco **los dígitos de inicio** , seleccione **exactamente** **7** del tipo en el campo de **longitud** y especificar **0** en **dígitos para quitar**, es la expresión regular resultante en el **modelo para que coincida con** :

    **^(\d{7})$**

7. En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos como se indica a continuación:
    - Un valor que represente la cantidad de dígitos especificada en el patrón de coincidencia. Por ejemplo, si el patrón coincidente es **^(\d{7})$**, a continuación, $1 en la regla de conversión representa los números marcados de 7 dígitos.
    - (Opcional) Escriba un valor en el campo **Dígitos que se agregarán** para especificar los dígitos que se agregarán al principio del número convertido (por ejemplo, **+1425**).
    
    Por ejemplo, si el **modelo de coincidencia** contiene **^(\d{7})$** que contenga el modelo para los números marcados y la **regla de conversión** **+ 1425$ 1** como el patrón de números de teléfono E.164, la regla 5550100 en + 14255550100.

8. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.
9. (Opcional) Especifique un número para probar la regla de normalización y después haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.
    > [!Note] 
    > Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante. Para obtener información detallada, vea [probar enrutamiento de voz](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx). 

10. Haga clic en **Aceptar** para guardar la regla de normalización.
11. Haga clic en **Aceptar** para guardar el plan de marcado.
12. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 
    > [!Note]
    > Cuando cree o cambie una regla de normalización, debe ejecutar el
comando Confirmar todo para publicar el cambio de configuración. Para obtener más información, consulte [Publicar cambios pendientes en la configuración de enrutamiento de voz](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Crear o modificar una regla de normalización manualmente

Complete los siguientes pasos si desea crear o modificar una regla de normalización de forma manual.

**Para definir una regla de normalización de forma manual**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener información detallada, vea [delegar permisos de instalación](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de Control. Para obtener información detallada sobre los distintos métodos que puede usar para iniciar el Skype para el Panel de Control, consulte [Install and open herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. (Opcional) Siga los pasos de [crear un plan de marcado](GET LINK AFTER MIGRATION) a través de paso 11 o [modificar un plan de marcado](GET LINK AFTER MIGRATION) hasta el paso 10.  
4. En **Nueva regla de normalización** o **Editar regla de normalización**, escriba un nombre que describa el patrón numérico que se normalizará en **Nombre** (por ejemplo, asigne a la regla de normalización el nombre **5DigitExtension**).
5. (Opcional) En **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").
6. En **Crear regla de normalización**, haga clic en **Editar**.
7. Especifique lo siguiente en Escribir una expresión regular:
    - En **Hacer coincidir este patrón**, especifique el patrón que desee usar para obtener como resultado el número de teléfono marcado.
    - En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos.

    Por ejemplo, si escribe **^(\d{7})$** en **este patrón de coincidencia** y **+ 1425$ 1** en la **regla de conversión**, la regla 5550100 en + 14255550100.

8. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.
9. (Opcional) Especifique un número para probar la regla de normalización y después haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.

    > [!Note]
    > Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante. Para obtener información detallada, vea [probar enrutamiento de voz](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx). 

10. Haga clic en **Aceptar** para guardar la regla de normalización.
11. Haga clic en **Aceptar** para guardar el plan de marcado.
12. En la página **Plan de marcado** , haga clic en t **Commi**y, a continuación, haga clic en **Confirmar todo**. 
