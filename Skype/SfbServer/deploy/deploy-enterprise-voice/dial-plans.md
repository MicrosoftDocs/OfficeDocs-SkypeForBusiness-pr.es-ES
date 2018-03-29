---
title: Crear o modificar un plan de marcado de Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
description: 'Resumen: Conozca cómo crear o modificar un plan de marcado mediante el Skype para el Panel de Control de servidor empresarial.'
ms.openlocfilehash: eaa2446c86b117558953416d0815a38371b205b1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-dial-plan-in-skype-for-business-server-2015"></a>Crear o modificar un plan de marcado de Skype Empresarial Server 2015
 
**Resumen:** Aprenda a crear o modificar un plan de marcado mediante el Skype para el Panel de Control de servidor empresarial.
  
### <a name="to-create-a-dial-plan"></a>Para crear un plan de marcado

1. Abre Skype para Panel de Control del servidor de empresa.
    
2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Plan de marcado**.
    
3. En la página **Plan de marcado**, haga clic en **Nuevo** y seleccione un ámbito para el plan de marcado:
    
   - **Plan de marcado de sitio** se aplica a un sitio en su totalidad, salvo a los usuarios o grupos que estén asignados a un plan de marcado de usuario. Si se selecciona el **sitio** para el ámbito de un plan de marcado, debe elegir el sitio desde el cuadro de diálogo **Seleccionar un sitio** . Si ya se ha creado un plan de marcado, el sitio no aparece en el cuadro de diálogo **Seleccionar un sitio**.
    
   - **Plan de marcado de grupo** se puede aplicar a una puerta de enlace de red telefónica conmutada (RTC) o a un registrador. Si selecciona **grupo** para el ámbito de un plan de marcado, seleccione la puerta de enlace PSTN o Registrar desde el cuadro de diálogo **Seleccione un servicio** . Si ya se ha creado un plan de marcado para un servicio (puerta de enlace de RTC o registrador), el servicio no aparece en la lista.
    
   - **Plan de marcado de usuario** se puede aplicar a usuarios o grupos específicos.
    
    > [!NOTE]
    > Una vez seleccionado el ámbito del plan de marcado, no se podrá cambiar. 
  
4. Si está creando un plan de marcado de usuario, escriba un nombre descriptivo en el campo **Nombre** en el cuadro de diálogo **Plan de marcado nuevo**. Una vez se haya guardado este nombre, no se podrá cambiar.
    
    > [!NOTE]
    > Para los planes de marcado de sitio, el campo **nombre** se rellena automáticamente con el nombre del sitio y no puede modificarse. > para planes de marcado de grupo, el campo **nombre** se rellena automáticamente con el nombre de registrador o puerta de enlace PSTN y no puede cambiarse.
  
5. El campo **Nombre simple** se cumplimenta previamente con el mismo nombre que aparece en el campo **Nombre**. Sil o desea, puede editar este campo para especificar un nombre más descriptivo que defina el sitio, servicio o usuario al que se aplica el plan de marcado.
    
    > [!IMPORTANT]
    > El  **Nombre simple** debe ser único entre todos los planes de marcado de la implementación. No debe superar los 256 caracteres Unicode, cada uno de los cuales puede ser un carácter alfabético o numérico, un guión (-), un punto (.) o un signo de subrayado (_). > caracteres **no admitidos** incluyen espacios y los caracteres reservados como se define en RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt). Caracteres reservados que **no admite** el **Nombre Simple** incluyen los siguientes: > ";" "?" "/" ":" "@" "&amp;" "=" "+""$","" 
  
6. (Opcional) En el campo **Descripción**, puede escribir información descriptiva adicional sobre el plan de marcado.
    
7. (Opcional) Si quiere usar este plan de marcado como región para los números de acceso telefónico local, especifique una **Región de conferencia de acceso telefónico local**. Si no quiere utilizar este plan de marcado para los números de acceso telefónico local, no rellene este campo. 
    
    > [!NOTE]
    > Se requiere que en las regiones de conferencia de acceso telefónico local se asocien los números de acceso a conferencias de acceso telefónico local con uno o más planes de marcado. 
  
8. (Opcional) En el campo **Prefijo de acceso externo**, especifique el valor únicamente si los usuarios necesitan marcar uno o más dígitos iniciales para tener acceso a una línea externa (por ejemplo, 9). Puede escribir un valor de prefijo de hasta cuatro caracteres (#, * y 0-9).
    
    > [!NOTE]
    > Si especifica un prefijo de acceso externo, no necesita crear una regla de normalización nueva para incluir el prefijo. 
  
9. Asocie y configure reglas de normalización para el plan de marcado tal como sigue:
    
    - Para elegir una o más reglas en una lista de todas las reglas de normalización en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. En **Seleccionar reglas de normalización**, resalte las reglas que desee asociar al plan de marcado y, a continuación, haga clic en **Aceptar**.
    
   - Para definir una regla de normalización nueva y asociarla con el plan de marcado, haga clic en **Nuevo**. Para obtener más información acerca de la definición de una nueva regla, consulte [crear o modificar una regla de normalización de Skype para el año 2015 Business](normalization-rules.md).
    
   - Para editar una regla de normalización que ya esté asociada al plan de marcado, resalte el nombre de la regla y haga clic en **Mostrar detalles**. 
    
   - Para copiar una regla de normalización existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, resalte el nombre de la regla y haga clic en **Copiar** y, a continuación, en **Pegar**. 
    
   - Para quitar una regla de normalización del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.
    
     > [!NOTE]
     > Cada plan de marcado debe tener al menos una regla de normalización asociada. Para obtener información acerca de cómo determinar todas las reglas de normalización de un dial plan requiere, vea [enrutamiento de Plan de voz saliente en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) en la documentación de planeamiento.
  
10. Compruebe que las reglas de normalización del plan de marcado se organizan en el orden correcto. Para cambiar la posición de la regla en la lista, resalte el nombre de la regla y haga clic en arriba o flecha abajo.
    
    > [!IMPORTANT]
    > Skype para Business Server recorre la lista de reglas de normalización desde la parte superior hacia abajo y utiliza la primera regla que coincida con el número marcado. Si configura un plan de marcado de forma que un número marcado pueda coincidir con más de una regla de normalización, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas. > El símbolo $ rule^(\d{11}) predeterminado de **Mantener todos los** normalización coincide con cualquier número de 11 dígitos. Por ejemplo, si agrega una regla de normalización que coincida con números de 11 dígitos que comiencen por 1425, asegúrese de que está ordenada **Guardar todos** debajo de la regla de $ restrictive^(1425\d{7}) más.
  
11. (Opcional) Especifique un número para probar el plan de marcado y, a continuación, haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.
    
12. Haga clic en **Aceptar**. 
    
13. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 
    
    > [!NOTE]
    > Cada vez que cree un plan de marcado, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte [publicación de cambios a la configuración de enrutamiento de voz de Skype para el año 2015 de negocios pendientes](voice-route-config-changes.md) en la documentación de las operaciones.
  
### <a name="to-modify-a-dial-plan"></a>Para modificar un plan de marcado

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como un miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, vea **Delegar permisos de instalación**.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Plan de marcado**.
    
4. En la página **Plan de marcado**, haga doble clic en el nombre del plan de marcado.
    
    > [!NOTE]
    > El ámbito y el nombre del plan de marcado se establecieron cuando se creó el plan de marcado. No pueden modificarse. 
  
5. (Opcional) En **Editar plan de marcado**, edite el campo **Nombre simple**, el cual se ha cumplimentado previamente con el mismo nombre que aparece en el campo **Nombre** para especificar un nombre más descriptivo que refleje el sitio, el servicio o el usuario a quien se aplica el plan de marcado.
    
    > [!IMPORTANT]
    > El **Nombre Simple** debe ser único entre todos los planes de marcado dentro de la implementación de Lync Server 2013. No debe superar los 256 caracteres Unicode, cada uno de los cuales puede ser un carácter alfabético o numérico, un guión (-), un punto (.), un signo más (+) o un signo de subrayado (_). > no se permiten espacios en el campo de **nombre sencillo** .
  
6. (Opcional) En el campo **Descripción**, escriba información descriptiva sobre el plan de marcado.
    
7. (Opcional) Si quiere usar este plan de marcado como región para los números de acceso telefónico local, especifique una **Región de conferencia de acceso telefónico local**. Si no quiere utilizar este plan de marcado para los números de acceso telefónico local, no rellene este campo. 
    
    > [!NOTE]
    > Se requiere que en las regiones de conferencia de acceso telefónico local se asocien los números de acceso a conferencias de acceso telefónico local con uno o más planes de marcado. 
  
8. (Opcional) En el campo **Prefijo de acceso externo**, especifique el valor únicamente si los usuarios necesitan marcar uno o más dígitos iniciales para tener acceso a una línea externa (por ejemplo, 9). Puede escribir un valor de prefijo de hasta cuatro caracteres (es decir, #, * y 0-9).
    
    > [!NOTE]
    > Si especifica un prefijo de acceso externo, no necesita crear una regla de normalización nueva para incluir el prefijo. 
  
9. Asocie y configure reglas de normalización para el plan de marcado:
    
   - Para elegir una o más reglas en una lista de todas las reglas de normalización en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. En el cuadro de diálogo **Seleccionar reglas de normalización**, resalte las reglas que desee asociar al plan de marcado y, a continuación, haga clic en **Aceptar**.
    
   - Para definir una regla de normalización nueva y asociarla con el plan de marcado, haga clic en **Nuevo**. Para obtener más información acerca de la definición de una nueva regla, consulte [crear o modificar una regla de normalización de Skype para el año 2015 Business](normalization-rules.md).
    
   - Para editar una regla de normalización que ya esté asociada al plan de marcado, resalte el nombre de la regla y haga clic en **Mostrar detalles**. 
    
   - Para copiar una regla de normalización existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, resalte el nombre de la regla y haga clic en **Copiar** y, a continuación, en **Pegar**. 
    
   - Para quitar una regla de normalización del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.
    
    > [!NOTE]
    > Cada plan de marcado debe tener al menos una regla de normalización asociada. Para obtener más información acerca de cómo determinar todas las reglas de normalización de un dial plan requiere, vea [enrutamiento de Plan de voz saliente en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) en la documentación de planeamiento.
  
10. Compruebe que las reglas de normalización del plan de marcado se organizan en el orden correcto. Para cambiar la posición de la regla en la lista, resalte el nombre de la regla y haga clic en arriba o flecha abajo.
    
    > [!IMPORTANT]
    > Skype para Business Server recorre la lista de reglas de normalización desde la parte superior hacia abajo y utiliza la primera regla que coincida con el número marcado. Si configura un plan de marcado de forma que un número marcado pueda coincidir con más de una regla de normalización, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas. > El símbolo $ rule^(\d{11}) predeterminado de **Mantener todos los** normalización coincide con cualquier número de 11 dígitos. Si, por ejemplo, agregar una regla de normalización que coincida con números de 11 dígitos que comiencen por 1425, asegúrese de que está ordenada **Guardar todos** debajo de la regla de $ restrictive^(1425\d{7}) más.
  
11. (Opcional) Especifique un número para probar el plan de marcado y, a continuación, haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.
    
    > [!NOTE]
    > Puede guardar un plan de marcado que no haya pasado la prueba aún y volver a configurarlo más adelante. Para obtener más información, vea [Pruebas de enrutamiento de voz](http://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx). 
  
12. Haga clic en **Aceptar**. 
    
13. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 
    
    > [!NOTE]
    > Siempre que cree o modifique un plan de marcado, debe ejecutar el comando **Confirmar todo** para publicar el cambio en la configuración. Para obtener más información, consulte [publicación de cambios a la configuración de enrutamiento de voz de Skype para el año 2015 de negocios pendientes](voice-route-config-changes.md) en la documentación de las operaciones.
  
## <a name="see-also"></a>Vea también

#### 

[Publicar los cambios pendientes a la configuración de enrutamiento de voz de Skype para negocios 2015](voice-route-config-changes.md)

