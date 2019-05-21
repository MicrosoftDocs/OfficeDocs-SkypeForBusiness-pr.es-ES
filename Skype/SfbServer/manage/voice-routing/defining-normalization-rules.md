---
title: Definir reglas de normalización en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Las reglas de normalización de Skype empresarial Server utilizan expresiones regulares de .NET Framework para traducir números de teléfono marcados al formato E. 164; en otras palabras, las reglas de normalización toman el número de teléfono marcado por un usuario y convierten ese número al formato usado internamente por Skype empresarial Server. Cada plan de marcado debe tener asignadas una o más reglas de normalización.
ms.openlocfilehash: e5156816de13a8d59e3e6eea4890046d5b4f586a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274985"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Definir reglas de normalización en Skype empresarial Server

Las reglas de normalización de Skype empresarial Server utilizan expresiones regulares de .NET Framework para traducir números de teléfono marcados al formato E. 164; en otras palabras, las reglas de normalización toman el número de teléfono marcado por un usuario y convierten ese número al formato usado internamente por Skype empresarial Server. Cada plan de marcado debe tener asignadas una o más reglas de normalización.

Para obtener más información sobre las reglas de normalización, consulte [planes de marcado y reglas](https://technet.microsoft.com/en-us/library/gg413082(v=ocs.15).aspx)de normalización.

Para obtener más información sobre cómo escribir expresiones regulares, vea [expresiones regulares de .NET Framework](http://go.microsoft.com/fwlink/p/?linkId=140927).

Puede usar cualquiera de los siguientes métodos para definir o editar una regla de normalización:
- [Use la herramienta **crear una regla** ](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) de normalización para especificar valores para los dígitos iniciales, la longitud, los dígitos que se van a quitar y los dígitos que se van a agregar y, a continuación, deje que el panel de control de Skype empresarial Server genere la regla de traducción y el patrón correspondiente. Para tí.
- [Escriba de forma manual expresiones regulares](#create-or-modify-a-normalization-rule-manually) para definir el patrón de coincidencia y la regla de traducción. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Crear o modificar una regla de normalización mediante la creación de una regla de normalización

Complete los pasos siguientes si desea crear o modificar una regla de normalización en el panel de control de Skype empresarial Server. 

**Para definir una regla mediante la creación de una regla de normalización**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración del delegado](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Skype para empresas, consulte [instalar y abrir herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Faculta Siga los pasos que se indican en [crear un plan de marcado](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan) mediante el paso 11 o [modificar un plan de marcado mediante el](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan) paso 10. 
4. En **Nueva regla de normalización** o **Editar regla de normalización**, escriba un nombre que describa el patrón numérico que se normalizará en **Nombre** (por ejemplo, **5DigitExtension**).
5. (Opcional) En **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").
6. En **Generar regla de normalización**, escriba valores en los siguientes campos:
    - **Dígitos iniciales**: (opcional) especifique los dígitos iniciales de los números marcados que desea que coincidan con el diseño. Por ejemplo, escriba **425** si desea que el patrón coincida con los números marcados que empiecen por 425.
    - **Length**: especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida exactamente con esta longitud, que coincide con números marcados que tienen al menos esta longitud o que coinciden con números marcados de cualquier longitud.
    - **Dígitos para quitar**: (opcional) especifique la cantidad de dígitos iniciales que quiere que se eliminen de los números marcados a los que desea que coincida el patrón.
    - **Dígitos para agregar**: (opcional) especifique los dígitos que desea agregar a los números marcados que desea que coincidan con el patrón.
    
    Los valores que introduzca en estos campos se reflejarán en **Patrón con el que coincidir** y **Regla de conversión**. Por ejemplo, si deja los **dígitos iniciales** en blanco, escriba **7** en el campo **longitud** , seleccione **exactamente**y especifique **0** en **dígitos para quitar**, la expresión regular resultante en el **patrón para coincidir** es:

    **^ (\d{7}) $**

7. En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos como se indica a continuación:
    - Un valor que represente la cantidad de dígitos especificada en el patrón de coincidencia. Por ejemplo, si el patrón correspondiente es **^ (\d{7}) $**, $1 en la regla de traducción representa los números marcados de 7 dígitos.
    - (Opcional) Escriba un valor en el campo **Dígitos que se agregarán** para especificar los dígitos que se agregarán al principio del número convertido (por ejemplo, **+1425**).
    
    Por ejemplo, si el **modelo que coincide** contiene **^ ({7}\d) $** como el patrón para los números marcados y la **regla de traducción** contiene **+ 1425 $1** como patrón para E. 164 números de teléfono, la regla normaliza 5550100 a + 14255550100.

8. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.
9. (Opcional) Especifique un número para probar la regla de normalización y después haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.
    > [!Note] 
    > Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante. Para obtener más información, consulte [probar el enrutamiento de voz](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx). 

10. Haga clic en **Aceptar** para guardar la regla de normalización.
11. Haga clic en **Aceptar** para guardar el plan de marcado.
12. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 
    > [!Note]
    > Cuando cree o cambie una regla de normalización, debe ejecutar el
comando Confirmar todo para publicar el cambio de configuración. Para obtener más información, vea [publicar cambios pendientes en la configuración del enrutamiento de voz](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Crear o modificar una regla de normalización manualmente

Complete los pasos siguientes si desea crear o modificar una regla de normalización de forma manual.

**Para definir una regla de normalización de forma manual**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración del delegado](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Skype para empresas, consulte [instalar y abrir herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Faculta Siga los pasos que se indican en [crear un plan de marcado](GET LINK AFTER MIGRATION) mediante el paso 11 o [modificar un plan de marcado mediante el](GET LINK AFTER MIGRATION) paso 10.  
4. En **Nueva regla de normalización** o **Editar regla de normalización**, escriba un nombre que describa el patrón numérico que se normalizará en **Nombre** (por ejemplo, asigne a la regla de normalización el nombre **5DigitExtension**).
5. (Opcional) En **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").
6. En **Crear regla de normalización**, haga clic en **Editar**.
7. Especifique lo siguiente en Escribir una expresión regular:
    - En **Hacer coincidir este patrón**, especifique el patrón que desee usar para obtener como resultado el número de teléfono marcado.
    - En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos.

    Por ejemplo, si escribe **^{7}(\d) $** en **coincidencia con este patrón** y **+ 1425 $1** en la regla de **traducción**, la regla normaliza 5550100 a + 14255550100.

8. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.
9. (Opcional) Especifique un número para probar la regla de normalización y después haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.

    > [!Note]
    > Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante. Para obtener más información, consulte [probar el enrutamiento de voz](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx). 

10. Haga clic en **Aceptar** para guardar la regla de normalización.
11. Haga clic en **Aceptar** para guardar el plan de marcado.
12. En la página **plan de marcado** , haga clic en **comunicaciones**y, a continuación, haga clic en **confirmar todo**. 
