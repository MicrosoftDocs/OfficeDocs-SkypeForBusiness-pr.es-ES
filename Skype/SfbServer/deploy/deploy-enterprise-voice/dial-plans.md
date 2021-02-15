---
title: Crear o modificar un plan de marcado en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
description: 'Resumen: obtenga información sobre cómo crear o modificar un plan de marcado mediante el Panel de control de Skype Empresarial Server.'
ms.openlocfilehash: 858ddf652d4c9308c5ec4088fb0d01d284318703
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831030"
---
# <a name="create-or-modify-a-dial-plan-in-skype-for-business-server"></a>Crear o modificar un plan de marcado en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo crear o modificar un plan de marcado mediante el Panel de control de Skype Empresarial Server.

### <a name="to-create-a-dial-plan"></a>Para crear un plan de marcado

1. Abra el Panel de control de Skype Empresarial Server.

2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Plan de marcado**.

3. En la página **Plan de marcado**, haga clic en **Nuevo** y seleccione un ámbito para el plan de marcado:

   - **Plan de marcado de sitio** se aplica a un sitio en su totalidad, salvo a los usuarios o grupos que estén asignados a un plan de marcado de usuario. Si selecciona Sitio **para** el ámbito de un plan de marcado, debe elegir el sitio en el cuadro de diálogo Seleccionar **un** sitio. Si ya se ha creado un plan de marcado, el sitio no aparece en el cuadro de diálogo **Seleccionar un sitio**.

   - **Plan de marcado de grupo** se puede aplicar a una puerta de enlace de red telefónica conmutada (RTC) o a un registrador. Si selecciona **Grupo para el** ámbito de un plan de marcado, elija la puerta de enlace RTC o el registrador en el cuadro de diálogo Seleccionar un servicio.  Si ya se ha creado un plan de marcado para un servicio (puerta de enlace de RTC o registrador), el servicio no aparece en la lista.

   - **Plan de marcado de usuario** se puede aplicar a usuarios o grupos especificados.

     > [!NOTE]
     > Una vez seleccionado el ámbito del plan de marcado, no se podrá cambiar.

4. Si está creando un plan de marcado de usuario, escriba un nombre descriptivo en el campo **Nombre** en el cuadro de diálogo **Plan de marcado nuevo**. Una vez se haya guardado este nombre, no se podrá cambiar.

    > [!NOTE]
    > Para los planes  de marcado de sitio, el campo Nombre se ha precarga con el  nombre del sitio y no se puede cambiar.> En el caso de los planes de marcado de grupo, el campo Nombre se ha precargado con el nombre del registrador o la puerta de enlace RTC y no se puede cambiar.

5. El campo **Nombre simple** se cumplimenta previamente con el mismo nombre que aparece en el campo **Nombre**. Opcionalmente, puede editar este campo para especificar un nombre más descriptivo que defina el sitio, servicio o usuario al que se aplica el plan de marcado.

   > [!IMPORTANT]
   > El **nombre simple** debe ser único entre todos los planes de marcado de la implementación. No puede superar los 256 caracteres Unicode, cada uno de los cuales puede ser un carácter alfabético o numérico,  un guión (-), un punto (.) o un carácter de subrayado (_).> Los caracteres no admitidos incluyen espacios y caracteres reservados como se define en RFC 3966 ( <http://www.ietf.org/rfc/rfc3966.txt> ). Entre los caracteres reservados **que no se** admiten en El nombre **simple** se incluyen los siguientes: > ";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","

6. (Opcional) En el campo **Descripción**, puede escribir información descriptiva adicional sobre el plan de marcado.

7. (Opcional) Si quiere usar este plan de marcado como región para los números de acceso telefónico local, especifique una **Región de conferencia de acceso telefónico local**. Si no quiere utilizar este plan de marcado para los números de acceso telefónico local, no rellene este campo.

    > [!NOTE]
    > Se requiere que en las regiones de conferencia de acceso telefónico local se asocien los números de acceso a conferencias de acceso telefónico local con uno o más planes de marcado.

8. (Opcional) En el campo **Prefijo de acceso externo**, especifique el valor únicamente si los usuarios necesitan marcar uno o más dígitos iniciales para tener acceso a una línea externa (por ejemplo, 9). Puede escribir un valor de prefijo de hasta cuatro caracteres (#, * y 0-9).

    > [!NOTE]
    > Si especifica un prefijo de acceso externo, no necesita crear una regla de normalización nueva para incluir el prefijo.

9. Asocie y configure reglas de normalización para el plan de marcado tal como sigue:

    - Para elegir una o más reglas de una lista de todas las reglas de normalización disponibles en la implementación Telefonía IP empresarial, haga clic en **Seleccionar**. En **Seleccionar reglas de normalización**, resalte las reglas que desee asociar al plan de marcado y, a continuación, haga clic en **Aceptar**.

   - Para definir una regla de normalización nueva y asociarla con el plan de marcado, haga clic en **Nuevo**. Para obtener más información sobre cómo definir una regla nueva, consulte Crear o modificar una regla [de normalización en Skype Empresarial.](normalization-rules.md)

   - Para editar una regla de normalización que ya esté asociada al plan de marcado, resalte el nombre de la regla y haga clic en **Mostrar detalles**.

   - Para copiar una regla de normalización existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, resalte el nombre de la regla y haga clic en **Copiar** y, a continuación, en **Pegar**.

   - Para quitar una regla de normalización del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.

     > [!NOTE]
     > Cada plan de marcado debe tener al menos una regla de normalización asociada. Para obtener información sobre cómo determinar todas las reglas de normalización que necesita un plan de marcado, consulte [Plan for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) en la documentación sobre planeación.

10. Compruebe que las reglas de normalización del plan de marcado están organizadas en el orden correcto. Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en la flecha arriba o abajo.

    > [!IMPORTANT]
    > Skype Empresarial Server recorre la lista de reglas de normalización de arriba abajo y usa la primera regla que coincide con el número marcado. Si configura un plan de marcado de forma que un número marcado pueda coincidir con más de una regla de normalización, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas. > la regla predeterminada **Mantener** todo normalización^(\d )$ coincide con cualquier número {11} de 11 dígitos. Por ejemplo, si agrega una regla de normalización que coincida con números de 11 dígitos que comiencen por 1425, asegúrese de que **Mantener** todo esté ordenado por debajo de la regla más restrictiva^(1425\d {7} )$.

11. (Opcional) Especifique un número para probar el plan de marcado y, a continuación, haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.

12. Haga clic en **Aceptar**.

13. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

    > [!NOTE]
    > Siempre que cree un plan de marcado, debe ejecutar el comando **Confirmar todo** para publicar el cambio en la configuración. Para obtener más información, [consulte Publicar los cambios pendientes en la configuración](voice-route-config-changes.md) de enrutamiento de voz en Skype Empresarial en la documentación de operaciones.

### <a name="to-modify-a-dial-plan"></a>Para modificar un plan de marcado

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol CsVoiceAdministrator, CsServerAdministrator, o CsAdministrator. Para obtener información detallada, consulte **Delegación de permisos de instalación**.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.

3. En la barra de navegación izquierda, haga clic en  **Enrutamiento de voz** y, a continuación, en  **Plan de marcado**.

4. En la página **Plan de marcado**, haga doble clic en el nombre del plan de marcado.

    > [!NOTE]
    > El ámbito y el nombre del plan de marcado se establecieron cuando se creó el plan de marcado. No pueden modificarse.

5. (Opcional) En **Editar plan de marcado**, edite el campo **Nombre simple**, el cual se ha cumplimentado previamente con el mismo nombre que aparece en el campo **Nombre** para especificar un nombre más descriptivo que refleje el sitio, el servicio o el usuario a quien se aplica el plan de marcado.

    > [!IMPORTANT]
    > El **nombre simple** debe ser único entre todos los planes de marcado de la implementación de Lync Server 2013. No puede superar los 256 caracteres Unicode, cada uno de los cuales puede ser un carácter alfabético o numérico, un guión (-), un  punto (.), un signo más (+) o un carácter de subrayado (_).> No se permiten espacios en el campo Nombre simple.

6. (Opcional) En el campo **Descripción**, escriba información descriptiva sobre el plan de marcado.

7. (Opcional) Si quiere usar este plan de marcado como región para los números de acceso telefónico local, especifique una **Región de conferencia de acceso telefónico local**. Si no quiere utilizar este plan de marcado para los números de acceso telefónico local, no rellene este campo.

    > [!NOTE]
    > Se requiere que en las regiones de conferencia de acceso telefónico local se asocien los números de acceso a conferencias de acceso telefónico local con uno o más planes de marcado.

8. (Opcional) En el campo **Prefijo de acceso externo**, especifique el valor únicamente si los usuarios necesitan marcar uno o más dígitos iniciales para tener acceso a una línea externa (por ejemplo, 9). Puede escribir un valor de prefijo de hasta cuatro caracteres (es decir, #, * y 0-9).

    > [!NOTE]
    > Si especifica un prefijo de acceso externo, no necesita crear una regla de normalización nueva para incluir el prefijo.

9. Asocie y configure reglas de normalización para el plan de marcado:

   - Para elegir una o más reglas de una lista de todas las reglas de normalización disponibles en la implementación Telefonía IP empresarial, haga clic en **Seleccionar**. En el cuadro de diálogo **Seleccionar reglas de normalización**, resalte las reglas que desee asociar al plan de marcado y, a continuación, haga clic en **Aceptar**.

   - Para definir una regla de normalización nueva y asociarla con el plan de marcado, haga clic en **Nuevo**. Para obtener más información sobre cómo definir una regla nueva, consulte Crear o modificar una regla [de normalización en Skype Empresarial.](normalization-rules.md)

   - Para editar una regla de normalización que ya esté asociada al plan de marcado, resalte el nombre de la regla y haga clic en **Mostrar detalles**.

   - Para copiar una regla de normalización existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, resalte el nombre de la regla y haga clic en **Copiar** y, a continuación, en **Pegar**.

   - Para quitar una regla de normalización del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.

     > [!NOTE]
     > Cada plan de marcado debe tener al menos una regla de normalización asociada. Para obtener más información sobre cómo determinar todas las reglas de normalización que necesita un plan de marcado, consulte [Plan for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) en la documentación sobre planeación.

10. Compruebe que las reglas de normalización del plan de marcado están organizadas en el orden correcto. Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en la flecha arriba o abajo.

    > [!IMPORTANT]
    > Skype Empresarial Server recorre la lista de reglas de normalización de arriba abajo y usa la primera regla que coincide con el número marcado. Si configura un plan de marcado de forma que un número marcado pueda coincidir con más de una regla de normalización, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas. > la regla predeterminada **Mantener** todo normalización^(\d )$ coincide con cualquier número {11} de 11 dígitos. Si, por ejemplo, agrega una regla de normalización que coincida con números de 11 dígitos que comiencen por 1425, asegúrese de que **Mantener** todo esté ordenado por debajo de la regla más restrictiva^(1425\d {7} )$.

11. (Opcional) Especifique un número para probar el plan de marcado y, a continuación, haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.

    > [!NOTE]
    > Puede guardar un plan de marcado que no haya pasado la prueba aún y volver a configurarlo más adelante. Para más información, consulte [Testing Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).

12. Haga clic en **Aceptar**.

13. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

    > [!NOTE]
    > Siempre que cree o modifique un plan de marcado, debe ejecutar el comando **Confirmar todo** para publicar el cambio en la configuración. Para obtener más información, [consulte Publicar los cambios pendientes en la configuración](voice-route-config-changes.md) de enrutamiento de voz en Skype Empresarial en la documentación de operaciones.

## <a name="see-also"></a>Vea también

[Publicar cambios pendientes en la configuración de enrutamiento de voz en Skype Empresarial](voice-route-config-changes.md)

