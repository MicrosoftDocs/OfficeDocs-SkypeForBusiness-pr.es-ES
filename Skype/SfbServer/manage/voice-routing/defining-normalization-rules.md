---
title: Definición de reglas de normalización en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Las reglas de normalización de Skype empresarial Server usan expresiones regulares de .NET Framework para traducir números de teléfono marcados al formato E. 164; es decir, las reglas de normalización toman el número de teléfono marcado por un usuario y convierten ese número al formato usado internamente por Skype empresarial Server. Cada plan de marcado debe tener asignadas una o más reglas de normalización.
ms.openlocfilehash: 42ec43a08d1c155f61869bdfebf07e94ac040e56
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028851"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Definición de reglas de normalización en Skype empresarial Server

Las reglas de normalización de Skype empresarial Server usan expresiones regulares de .NET Framework para traducir números de teléfono marcados al formato E. 164; es decir, las reglas de normalización toman el número de teléfono marcado por un usuario y convierten ese número al formato usado internamente por Skype empresarial Server. Cada plan de marcado debe tener asignadas una o más reglas de normalización.

Para obtener más información acerca de las reglas de normalización, consulte [planes de marcado y reglas de normalización](https://technet.microsoft.com/library/gg413082(v=ocs.15).aspx).

Para obtener información detallada sobre cómo escribir expresiones regulares, vea [expresiones regulares de .NET Framework](http://go.microsoft.com/fwlink/p/?linkId=140927).

Puede usar cualquiera de los siguientes métodos para definir o editar una regla de normalización:
- [Use la herramienta **crear una regla de normalización** ](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) para especificar valores para los dígitos iniciales, la longitud, los dígitos que se van a quitar y los dígitos que se van a agregar y, a continuación, deje que el panel de control de Skype empresarial Server genere el patrón de coincidencia y la regla de conversión correspondientes.
- [Escriba manualmente las expresiones regulares](#create-or-modify-a-normalization-rule-manually) para definir el patrón de coincidencia y la regla de conversión. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Creación o modificación de una regla de normalización mediante la creación de una regla de normalización

Complete los pasos siguientes si desea crear o modificar una regla de normalización en el panel de control de Skype empresarial Server. 

**Para definir una regla mediante Generar regla de normalización**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Skype empresarial, consulte [instalar y abrir las herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Opcional Siga los pasos que se indican en [crear un plan de marcado mediante el](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan) paso 11 o [modificar un plan de marcado hasta el](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan) paso 10. 
4. En **Nueva regla de normalización** o **Editar regla de normalización**, escriba un nombre que describa el patrón numérico que se normalizará en **Nombre** (por ejemplo, **Extension5digitos**).
5. (Opcional) En **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").
6. En **Generar regla de normalización**, escriba valores en los siguientes campos:
    - **Dígitos iniciales**: (opcional) especifique los dígitos iniciales de los números marcados a los que desea que corresponda el patrón. Por ejemplo, escriba **425** si desea que el patrón coincida con los números marcados que empiecen por 425.
    - **Longitud**: especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida exactamente con esta longitud, que coincida con números marcados que tengan como mínimo esta longitud o que coincidan con números marcados de cualquier longitud.
    - **Dígitos que**se quitarán: (opcional) especifique el número de dígitos iniciales que se quitarán de los números marcados con los que desea que se haga coincidir el patrón.
    - **Dígitos que**se agregarán: (opcional) especifique los dígitos que se agregarán a los números marcados con los que desea que se ajuste la trama.
    
    Los valores que introduzca en estos campos se reflejarán en **Patrón con el que hacer coincidir** y **Regla de conversión**. Por ejemplo, si deja los **dígitos iniciales** vacíos, escribe **7** en el campo **longitud** , selecciona **exactamente**y especifica **0** en **dígitos para quitarlo**, la expresión regular resultante en el **patrón para coincidir** es:

    **^ (\d{7}) $**

7. En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos, así:
    - Un valor que represente la cantidad de dígitos especificada en el patrón de coincidencia. Por ejemplo, si el patrón de coincidencia es **^ ({7}\d) $**, $1 en la regla de conversión representa números marcados de 7 dígitos.
    - (Opcional) Escriba un valor en el campo **Dígitos que se agregarán** para especificar los dígitos que se agregarán al principio del número convertido (por ejemplo, **+1425**).
    
    Por ejemplo, si el **modelo que debe coincidir** contiene **^ (\d{7}) $** como el patrón para los números marcados y la regla de **conversión** contiene **+ 1425 $1** como modelo para los números de teléfono e. 164, la regla normaliza 5550100 a + 14255550100.

8. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.
9. (Opcional) Especifique un número para probar la regla de normalización y después haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.
    > [!Note] 
    > Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante. Para obtener más información, consulte [probar el enrutamiento de voz](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx). 

10. Haga clic en **Aceptar** para guardar la regla de normalización.
11. Haga clic en **Aceptar** para guardar el plan de marcado.
12. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 
    > [!Note]
    > Cada vez que cree o cambie una regla de normalización, debe ejecutar el comando Confirmar todo para publicar el cambio de configuración. Para obtener información detallada, consulte [Publish Pending changes to the Voice Routing Configuration](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx). 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Crear o modificar una regla de normalización manualmente

Siga los pasos que se muestran a continuación si desea crear o modificar manualmente una regla de normalización.

**Para definir una regla de normalización de forma manual**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Skype empresarial, consulte [instalar y abrir las herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Opcional Siga los pasos que se indican en [crear un plan de marcado mediante el](GET LINK AFTER MIGRATION) paso 11 o [modificar un plan de marcado hasta el](GET LINK AFTER MIGRATION) paso 10.  
4. En **Nueva regla de normalización** o **Editar regla de normalización**, escriba un nombre que describa el patrón numérico que se normalizará en **Nombre** (por ejemplo, llame a la regla de normalización **Extension5digitos**).
5. (Opcional) En **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").
6. En **Generar regla de normalización**, haga clic en **Editar**.
7. Especifique lo siguiente en Escribir una expresión regular:
    - En **Hacer coincidir este patrón**, especifique el patrón que desee usar para obtener como resultado el número de teléfono marcado.
    - En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos.

    Por ejemplo, si escribe **{7}^ (\d) $** en **coincidir con este patrón** y **+ 1425 $1** en la **regla de conversión**, la regla normaliza 5550100 a + 14255550100.

8. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.
9. (Opcional) Especifique un número para probar la regla de normalización y después haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.

    > [!Note]
    > Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante. Para obtener más información, consulte [probar el enrutamiento de voz](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx). 

10. Haga clic en **Aceptar** para guardar la regla de normalización.
11. Haga clic en **Aceptar** para guardar el plan de marcado.
12. En la página **plan de marcado** , haga clic en **commi**y, a continuación, haga clic en **confirmar todo**. 
