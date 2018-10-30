---
title: 'Lync Server 2013: Presentación del id. de autor de llamada'
TOCTitle: Presentación del id. de autor de llamada
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204980(v=OCS.15)
ms:contentKeyID: 48275584
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Presentación del id. de autor de llamada en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-22_

Con Lync Server 2010, el número de teléfono que recibe la llamada (es decir, el número de teléfono al que se llama) se puede traducir del formato E.164 al formato de marcado local que el *tronco de mismo nivel* necesita (es decir, la puerta de enlace asociada, la central de conmutación (PBX) o el tronco SIP). Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.

Lync Server 2013 ofrece la opción de convertir también el número de teléfono de la parte que llama (es decir, el número de teléfono desde el que llama realiza la llamada) del formato E.164 al formato de marcación local que requiere el tronco. Por ejemplo, puede escribir una regla de conversión para quitar el prefijo +34 del principio de una cadena de llamada y sustituirlo por 0134.

**Para configurar el identificador de llamada con el Panel de control de Lync Server**

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco** .

4.  En la página **Configuración de tronco** , haga doble clic en el tronco existente (por ejemplo, **Global** ) para abrir el cuadro de diálogo **Editar configuración de tronco** .

5.  Para configurar la presentación del identificador de llamada:
    
      - Para elegir una o más reglas en una lista de reglas de conversión disponible en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar** . En **Reglas de conversión del número que llama** , haga clic en las reglas que quiera asociar al tronco y, después, haga clic en **Aceptar** .
    
      - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva** . Para obtener información sobre cómo definir una regla nueva, consulte [Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación referente a la implementación.
    
      - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en **Mostrar detalles** . Para obtener más información, consulte [Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.
    
      - Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en **Pegar** . Para obtener información detallada, consulte [Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar** .
    
    > [!WARNING]  
	> No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas pudieran entrar en conflicto.

