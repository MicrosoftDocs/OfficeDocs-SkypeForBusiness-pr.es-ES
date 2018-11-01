---
title: 'Lync Server 2013: Crear un plan de marcado'
TOCTitle: Crear un plan de marcado
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398909(v=OCS.15)
ms:contentKeyID: 48276775
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear un plan de marcado en Lync Server 2013

 

_**Última modificación del tema:** 2013-10-24_

Para crear un plan de marcado nuevo, siga los pasos del procedimiento a continuación. Si desea editar un plan de marcado, consulte [Modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

## Para crear un plan de marcado

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Plan de marcado**.

4.  En la página **Plan de marcado**, haga clic en **Nuevo** y seleccione un ámbito para el plan de marcado:
    
      - **Plan de marcado de sitio** se aplica a un sitio en su totalidad, salvo a los usuarios o grupos que estén asignados a un plan de marcado de usuario. Si selecciona **Sitio** para el ámbito de un plan de marcado, debe elegir el sitio en el cuadro de diálogo **Seleccionar un sitio** . Si ya se ha creado un plan de marcado, el sitio no aparece en el cuadro de diálogo **Seleccionar un sitio** .
    
      - **Plan de marcado de grupo** se puede aplicar a una puerta de enlace de red telefónica conmutada (RTC) o a un registrador. Si selecciona **Grupo** para el ámbito de un plan de marcado, elija la puerta de enlace de RTC o el registrador en el cuadro de diálogo **Seleccionar un servicio**. Si ya se ha creado un plan de marcado para un servicio (puerta de enlace de RTC o registrador), el servicio no aparece en la lista.
    
      - **Plan de marcado de usuario** se puede aplicar a usuarios o grupos especificados.
    

    > [!NOTE]
    > Una vez seleccionado el ámbito del plan de marcado, no se podrá cambiar.



5.  Si está creando un plan de marcado de usuario, escriba un nombre descriptivo en el campo **Nombre** en el cuadro de diálogo **Plan de marcado nuevo**. Una vez se haya guardado este nombre, no se podrá cambiar.
    

    > [!NOTE]
    > Respecto a los planes de marcado de sitio, el campo <STRONG>Nombre</STRONG> se cumplimenta previamente con el nombre del sitio y no se puede modificar.<BR>Respecto a los planes de marcado de grupo, el campo <STRONG>Nombre</STRONG> se cumplimenta previamente con la puerta de enlace de RTC o el registrador y no se puede modificar.



6.  El campo **Nombre simple** se cumplimenta previamente con el mismo nombre que aparece en el campo **Nombre**. Opcionalmente, puede editar este campo para especificar un nombre más descriptivo que defina el sitio, servicio o usuario al que se aplica el plan de marcado.
    
    > [!IMPORTANT]  
	> El <strong>Nombre simple</strong> debe ser único entre todos los planes de marcado de la implementación de Lync Server. No puede exceder los 256 caracteres Unicode, donde cada uno de los cuales puede ser alfanumérico o numérico, un guión (-), un punto (.), o un guión bajo (_).<br />
    > Algunos caracteres <strong>no admitidos</strong> son los espacios y lo caracteres reservados, según se define en RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt). Algunos de los caracteres reservados <strong>no admitidos</strong> en el <strong>Nombre simple</strong> son los siguientes:<br />
    > &quot;;&quot; &quot;/&quot; &quot;?&quot; &quot;:&quot; &quot;@&quot; &quot;&amp;&quot; &quot;=&quot; &quot;+&quot; &quot;$&quot; &quot;,&quot;


7.  (Opcional) En el campo **Descripción**, puede escribir información descriptiva adicional sobre el plan de marcado.

8.  (Opcional) Si quiere usar este plan de marcado como región para los números de acceso telefónico local, especifique una **Región de conferencia de acceso telefónico local**. Si no quiere utilizar este plan de marcado para los números de acceso telefónico local, no rellene este campo.
    

    > [!NOTE]
    > Se requiere que en las regiones de conferencia de acceso telefónico local se asocien los números de acceso a conferencias de acceso telefónico local con uno o más planes de marcado.



9.  (Opcional) En el campo **Prefijo de acceso externo**, especifique el valor únicamente si los usuarios necesitan marcar uno o más dígitos iniciales para tener acceso a una línea externa (por ejemplo, 9). Puede escribir un valor de prefijo de hasta cuatro caracteres (\#, \* y 0-9).
    

    > [!NOTE]
    > Si especifica un prefijo de acceso externo, no necesita crear una regla de normalización nueva para incluir el prefijo.



10. Asocie y configure reglas de normalización para el plan de marcado tal como sigue:
    
      - Para elegir una o más reglas en una lista con todas las reglas de normalización disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. En **Seleccionar reglas de normalización**, resalte las reglas que desee asociar al plan de marcado y, a continuación, haga clic en **Aceptar**.
    
      - Para definir una regla de normalización nueva y asociarla con el plan de marcado, haga clic en **Nuevo**. Para más información sobre cómo definir una regla nueva, consulte [Definir las reglas de normalización en Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Para editar una regla de normalización que ya esté asociada al plan de marcado, resalte el nombre de la regla y haga clic en **Mostrar detalles**. Para más información sobre cómo editar la regla, consulte [Definir las reglas de normalización en Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Para copiar una regla de normalización existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, resalte el nombre de la regla y haga clic en **Copiar** y, a continuación, en **Pegar**. Para más información sobre cómo editar la copia, consulte [Definir las reglas de normalización en Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Para quitar una regla de normalización del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.
    

    > [!NOTE]
    > Cada plan de marcado debe tener al menos una regla de normalización asociada. Para obtener información sobre cómo determinar todas las reglas de normalización que necesita un plan de marcado, consulte <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Planes de marcado y reglas de normalización en Lync Server 2013</A> en la documentación referente a la planeación.



11. Compruebe que las reglas de normalización del plan de marcado están dispuestas en el orden correcto. Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en la flecha arriba o abajo.
    
    > [!IMPORTANT]  
    > Lync Server recorre la lista de reglas de normalización de arriba abajo y utiliza la primera regla que coincide con el número marcado. Si configura un plan de marcado de forma que un número marcado pueda coincidir con más de una regla de normalización, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas.<br />
    > La regla de normalización predeterminada <strong>^(\d{11})$</strong> de <strong>Prefix All</strong> coincide con cualquier número de 11 dígitos. Por ejemplo, si agrega una regla de normalización que coincide con números de 11 dígitos que comiencen con 1425, asegúrese de que <strong>Prefix All</strong> se encuentra debajo de la regla <strong>^(1425\d{7})$</strong> más restrictiva.


12. (Opcional) Especifique un número para probar el plan de marcado y, a continuación, haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.
    

    > [!NOTE]
    > Puede guardar un plan de marcado que no haya pasado la prueba aún y volver a configurarlo más adelante. Para más información, consulte <A href="lync-server-2013-test-voice-routing.md">Probar el enrutamiento de voz en Lync Server 2013</A>.



13. Haga clic en**Aceptar**.

14. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    

    > [!NOTE]
    > Siempre que cree un plan de marcado, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio en la configuración. Para más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</A> en la documentación referente a las operaciones.



## Vea también

#### Tareas

[Modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Otros recursos

[Definir las reglas de normalización en Lync Server 2013](lync-server-2013-defining-normalization-rules.md)

