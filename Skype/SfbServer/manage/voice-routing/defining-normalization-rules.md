---
title: Definición de reglas de normalización en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Las reglas de normalización de Skype Empresarial Server .NET Framework expresiones regulares para traducir números de teléfono marcados al formato E.164; en otras palabras, las reglas de normalización toman el número de teléfono marcado por un usuario y convierten ese número al formato usado internamente por Skype Empresarial Server. Cada plan de marcado debe tener asignadas una o más reglas de normalización.
ms.openlocfilehash: 1be34e5c40a4da4e9def4de294ece134f2fe229d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120922"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Definición de reglas de normalización en Skype Empresarial Server

Las reglas de normalización de Skype Empresarial Server .NET Framework expresiones regulares para traducir números de teléfono marcados al formato E.164; en otras palabras, las reglas de normalización toman el número de teléfono marcado por un usuario y convierten ese número al formato usado internamente por Skype Empresarial Server. Cada plan de marcado debe tener asignadas una o más reglas de normalización.

Para obtener más información sobre las reglas de normalización, vea [Planes de marcado y reglas de normalización.](/previous-versions/office/lync-server-2013/lync-server-2013-dial-plans-and-normalization-rules)

Para obtener más información sobre cómo escribir expresiones regulares, [vea .NET Framework Regular Expressions](/dotnet/standard/base-types/regular-expressions).

Puede usar cualquiera de los siguientes métodos para definir o editar una regla de normalización:
- Use la herramienta Crear una regla de [ **normalización**](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) para especificar los valores de los dígitos iniciales, la longitud, los dígitos que se quitarán y los dígitos que se agregarán y, a continuación, deje que el Panel de control de Skype Empresarial Server genere el patrón de coincidencia y la regla de traducción correspondientes.
- [Escriba expresiones regulares manualmente](#create-or-modify-a-normalization-rule-manually) para definir el patrón de coincidencia y la regla de traducción. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Crear o modificar una regla de normalización mediante Crear una regla de normalización

Complete los pasos siguientes si desea crear o modificar una regla de normalización en el Panel de control de Skype Empresarial Server. 

**Para definir una regla mediante Generar regla de normalización**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, vea [Delegate setup permissions](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control. Para obtener información detallada sobre los diferentes métodos que puede usar para iniciar el Panel de control de Skype Empresarial, vea [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).
3. (Opcional) Siga los pasos descritos en [Create a dial plan](../../deploy/deploy-enterprise-voice/dial-plans.md#to-create-a-dial-plan) through step 11 o Modify a dial [plan](../../deploy/deploy-enterprise-voice/dial-plans.md#to-modify-a-dial-plan) through step 10. 
4. En **Nueva regla de normalización** o **Editar regla de normalización**, escriba un nombre que describa el patrón numérico que se normalizará en **Nombre** (por ejemplo, **Extension5digitos**).
5. (Opcional) En **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").
6. En **Generar regla de normalización**, escriba valores en los siguientes campos:
    - **Dígitos iniciales**: (opcional) Especifique los dígitos iniciales de los números marcados que desea que coincidan con el patrón. Por ejemplo, escriba **425** si desea que el patrón coincida con los números marcados que empiecen por 425.
    - **Length:** especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida exactamente con esta longitud, que coincida con los números marcados que tienen al menos esta longitud, o si coincide con los números marcados de cualquier longitud.
    - **Dígitos para quitar**: (opcional) Especifique el número de dígitos iniciales que se quitarán de los números marcados que desea que coincida el patrón.
    - **Dígitos para agregar**: (opcional) Especifique los dígitos que se agregarán a los números marcados que desee que coincidan con el patrón.
    
    Los valores que introduzca en estos campos se reflejarán en **Patrón con el que hacer coincidir** y **Regla de conversión**. Por ejemplo, si  deja los dígitos iniciales vacíos, escriba **7** en el campo Longitud seleccione Exactamente y especifique **0** en  **Dígitos** para quitar , la expresión regular resultante en el patrón que se va a **coincidir** es: 

    **^(\d {7} )$**

7. En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos, así:
    - Un valor que represente la cantidad de dígitos especificada en el patrón de coincidencia. Por ejemplo, si el patrón de coincidencia es **^(\d {7} )$**, $1 en la regla de traducción representa números marcados de 7 dígitos.
    - (Opcional) Escriba un valor en el campo **Dígitos que se agregarán** para especificar los dígitos que se agregarán al principio del número convertido (por ejemplo, **+1425**).
    
    Por ejemplo, si **Pattern to match** contiene **^(\d {7} )$** como el patrón para números marcados y la regla de traducción contiene **+1425$1** como patrón para números de teléfono E.164, la regla normaliza 5550100 a +1425550100. 

8. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.
9. (Opcional) Especifique un número para probar la regla de normalización y después haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.
    > [!Note] 
    > Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante. Para obtener más información, vea [Test voice routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing). 

10. Haga clic en **Aceptar** para guardar la regla de normalización.
11. Haga clic en **Aceptar** para guardar el plan de marcado.
12. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 
    > [!Note]
    > Cada vez que cree o cambie una regla de normalización, debe ejecutar el comando Confirmar todo para publicar el cambio de configuración. Para obtener más información, [vea Publicar cambios pendientes en la configuración de enrutamiento de voz.](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration) 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Crear o modificar una regla de normalización manualmente

Siga los pasos que se muestran a continuación si desea crear o modificar manualmente una regla de normalización.

**Para definir una regla de normalización de forma manual**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, vea [Delegate setup permissions](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control. Para obtener información detallada sobre los diferentes métodos que puede usar para iniciar el Panel de control de Skype Empresarial, vea [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).
3. (Opcional) Siga los pasos descritos en [Create a dial plan](GET LINK AFTER MIGRATION) through step 11 o Modify a dial [plan](GET LINK AFTER MIGRATION) through step 10.  
4. En **Nueva regla de normalización** o **Editar regla de normalización**, escriba un nombre que describa el patrón numérico que se normalizará en **Nombre** (por ejemplo, llame a la regla de normalización **Extension5digitos**).
5. (Opcional) En **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").
6. En **Generar regla de normalización**, haga clic en **Editar**.
7. Especifique lo siguiente en Escribir una expresión regular:
    - En **Hacer coincidir este patrón**, especifique el patrón que desee usar para obtener como resultado el número de teléfono marcado.
    - En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos.

    Por ejemplo, si escribe **^(\d {7} )$** en Coincidir con este patrón y **+1425$1** en la regla de **traducción,** la regla normaliza 5550100 a +1425550100. 

8. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.
9. (Opcional) Especifique un número para probar la regla de normalización y después haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.

    > [!Note]
    > Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante. Para obtener más información, vea [Test voice routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing). 

10. Haga clic en **Aceptar** para guardar la regla de normalización.
11. Haga clic en **Aceptar** para guardar el plan de marcado.
12. En la **página Plan de** marcado, haga clic en **Commi** t y, a continuación, haga clic **en Confirmar todo**.