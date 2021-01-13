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
description: Las reglas de normalización de Skype Empresarial Server usan expresiones regulares de .NET Framework para traducir los números de teléfono marcados al formato E.164; en otras palabras, las reglas de normalización toman el número de teléfono marcado por un usuario y convierten ese número al formato usado internamente por Skype Empresarial Server. Cada plan de marcado debe tener asignadas una o más reglas de normalización.
ms.openlocfilehash: d4e248dc9b814610df544bca9d932a29756a80b0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823380"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Definición de reglas de normalización en Skype Empresarial Server

Las reglas de normalización de Skype Empresarial Server usan expresiones regulares de .NET Framework para traducir los números de teléfono marcados al formato E.164; en otras palabras, las reglas de normalización toman el número de teléfono marcado por un usuario y convierten ese número al formato usado internamente por Skype Empresarial Server. Cada plan de marcado debe tener asignadas una o más reglas de normalización.

Para obtener más información acerca de las reglas de normalización, consulte [Planes de marcado y reglas de normalización.](https://technet.microsoft.com/library/gg413082(v=ocs.15).aspx)

Para obtener más información sobre cómo escribir expresiones regulares, vea [.NET Framework Regular Expressions](https://go.microsoft.com/fwlink/p/?linkId=140927).

Puede usar cualquiera de los siguientes métodos para definir o editar una regla de normalización:
- Use la herramienta Crear una regla de [ **normalización**](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) para especificar los valores de los dígitos iniciales, la longitud, los dígitos que se quitarán y los dígitos que se agregarán y, a continuación, deje que el Panel de control de Skype Empresarial Server genere automáticamente el patrón de coincidencia y la regla de conversión correspondientes.
- [Escribir expresiones regulares manualmente para](#create-or-modify-a-normalization-rule-manually) definir el patrón de coincidencia y la regla de conversión. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Crear o modificar una regla de normalización mediante la creación de una regla de normalización

Complete los pasos siguientes si desea crear o modificar una regla de normalización en el Panel de control de Skype Empresarial Server. 

**Para definir una regla mediante Generar regla de normalización**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, vea [Delegar permisos de configuración.](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el Panel de control de Skype Empresarial, consulte Instalar y [abrir herramientas administrativas.](../../management-tools/install-and-open-administrative-tools.md)
3. (Opcional) Siga los pasos descritos en [Crear un plan de marcado](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan) hasta el paso 11 o Modificar un plan de marcado [hasta](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan) el paso 10. 
4. En **Nueva regla de normalización** o **Editar regla de normalización**, escriba un nombre que describa el patrón numérico que se normalizará en **Nombre** (por ejemplo, **Extension5digitos**).
5. (Opcional) En **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").
6. En **Generar regla de normalización**, escriba valores en los siguientes campos:
    - **Dígitos iniciales:**(opcional) Especifique los dígitos iniciales de los números marcados que desea que coincidan con el patrón. Por ejemplo, escriba **425** si desea que el patrón coincida con los números marcados que empiecen por 425.
    - **Longitud:** especifique el número de dígitos del patrón de coincidencia y seleccione si desea que el patrón coincida exactamente con esta longitud, con los números marcados que tienen al menos esta longitud o con los números marcados de cualquier longitud.
    - **Dígitos para quitar:**(opcional) Especifique el número de dígitos iniciales que se quitarán de los números marcados que desea que coincidan con el patrón.
    - **Dígitos para agregar:**(opcional) Especifique los dígitos que se agregarán a los números marcados que desea que coincidan con el patrón.
    
    Los valores que introduzca en estos campos se reflejarán en **Patrón con el que hacer coincidir** y **Regla de conversión**. Por ejemplo, si  deja los dígitos iniciales vacíos, escriba **7** en el campo Longitud , seleccione Exactamente y especifique **0** en Dígitos para quitar , la expresión regular resultante en el  **patrón** que debe coincidir es:  

    **^(\d {7} )$**

7. En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos, así:
    - Un valor que represente la cantidad de dígitos especificada en el patrón de coincidencia. Por ejemplo, si el patrón de coincidencia es **^(\d {7} )$**, $1 en la regla de conversión representa números marcados de 7 dígitos.
    - (Opcional) Escriba un valor en el campo **Dígitos que se agregarán** para especificar los dígitos que se agregarán al principio del número convertido (por ejemplo, **+1425**).
    
    Por ejemplo, si pattern **to match** contiene **^(\d {7} )$** como patrón para números marcados y la regla de conversión contiene **+1425$1** como patrón para números de teléfono E.164, la regla normaliza de 5550100 a +14255550100. 

8. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.
9. (Opcional) Especifique un número para probar la regla de normalización y después haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.
    > [!Note] 
    > Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante. Para obtener más información, consulte [Probar enrutamiento de voz.](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx) 

10. Haga clic en **Aceptar** para guardar la regla de normalización.
11. Haga clic en **Aceptar** para guardar el plan de marcado.
12. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 
    > [!Note]
    > Cada vez que cree o cambie una regla de normalización, debe ejecutar el comando Confirmar todo para publicar el cambio de configuración. Para obtener más información, [consulte Publicar cambios pendientes en la configuración de enrutamiento de voz.](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx) 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Crear o modificar una regla de normalización manualmente

Siga los pasos que se muestran a continuación si desea crear o modificar manualmente una regla de normalización.

**Para definir una regla de normalización de forma manual**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, vea [Delegar permisos de configuración.](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el Panel de control de Skype Empresarial, consulte Instalar y [abrir herramientas administrativas.](../../management-tools/install-and-open-administrative-tools.md)
3. (Opcional) Siga los pasos descritos en [Crear un plan de marcado](GET LINK AFTER MIGRATION) hasta el paso 11 o Modificar un plan de marcado [hasta](GET LINK AFTER MIGRATION) el paso 10.  
4. En **Nueva regla de normalización** o **Editar regla de normalización**, escriba un nombre que describa el patrón numérico que se normalizará en **Nombre** (por ejemplo, llame a la regla de normalización **Extension5digitos**).
5. (Opcional) En **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").
6. En **Generar regla de normalización**, haga clic en **Editar**.
7. Especifique lo siguiente en Escribir una expresión regular:
    - En **Hacer coincidir este patrón**, especifique el patrón que desee usar para obtener como resultado el número de teléfono marcado.
    - En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos.

    Por ejemplo, si escribe **^(\d {7} )$** en Coincidir con este patrón y **+1425$1** en la regla de **conversión,** la regla normaliza de 5550100 a +14255550100. 

8. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.
9. (Opcional) Especifique un número para probar la regla de normalización y después haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.

    > [!Note]
    > Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante. Para obtener más información, consulte [Probar enrutamiento de voz.](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx) 

10. Haga clic en **Aceptar** para guardar la regla de normalización.
11. Haga clic en **Aceptar** para guardar el plan de marcado.
12. En la **página Plan de** marcado, haga clic en **Commi** t y, a continuación, haga clic **en Confirmar todo**. 
