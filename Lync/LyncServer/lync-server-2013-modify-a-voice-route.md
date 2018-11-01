﻿---
title: Modificar una ruta de voz en Lync Server 2013
TOCTitle: Modificar una ruta de voz en Lync Server 2013
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48276359
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modificar una ruta de voz en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

En este tema se describe cómo editar una ruta de voz. Para crear una ruta nueva, consulte [Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).

## Para modificar una ruta de voz

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Ruta**.

4.  En la página **Ruta**, use uno de los métodos siguientes para modificar una ruta de voz:
    
      - Haga clic en el nombre de una ruta de voz, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.
    
      - Haga clic en el nombre de una ruta de voz, haga clic en **Editar**, en **Copiar** y, a continuación, en **Pegar**. Haga clic en la copia nueva de la ruta de voz que acaba de crear, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.

5.  En el campo **Nombre** en la página **Editar ruta de voz**, escriba un nombre descriptivo para la ruta de voz.

6.  (Opcional) En el campo **Descripción**, escriba información descriptiva adicional para la ruta de voz.

7.  Para especificar los patrones que desea que incluya esta ruta, puede utilizar la herramienta **Crear un patrón de coincidencia** para generar una expresión regular o escribirla manualmente.
    
      - Para usar la herramienta **Crear un patrón de coincidencia** con el fin de generar una expresión regular, especifique valores de la forma siguiente: Puede especificar dos tipos de patrón de coincidencia:
        
          - **Dígitos iniciales para números que quiera permitir:** Introduzca los valores de prefijo que debe incluir esta ruta (incluso el signo + inicial, si fuera necesario). Por ejemplo, escriba **+425** y, a continuación, haga clic en **Agregar**. Repita el procedimiento para cada valor de prefijo que desee incluir en la ruta.
        
          - **Excepciones:** Si desea especificar una o más excepciones para un valor de prefijo, resalte el prefijo y haga clic en **Excepciones**. Escriba uno o más valores para los patrones coincidentes que *no* quiere que se incluyan en esta ruta. Por ejemplo, para excluir los números que comiencen por +425237 de la ruta, escriba un valor de **+425237** en el campo **Excepciones** y, a continuación, haga clic en **Aceptar**.
    
      - Para definir manualmente el patrón coincidente, haga clic en **Editar** en la herramienta **Crear un patrón de coincidencia** y, a continuación, escriba una expresión regular de .NET Framework para especificar el patrón coincidente correspondiente a los números de teléfono de destino a los que se va a aplicar la ruta. Para obtener información acerca de cómo escribir expresiones regulares, consulte "Expresiones regulares de .NET Framework" en [http://go.microsoft.com/fwlink/?linkid=140927\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=140927%26clcid=0xc0a).

8.  Seleccione **Suprimir Id. de autor de llamada** si no desea que el Id. del teléfono desde donde se efectúa la llamada saliente se muestre al receptor de la llamada. Si selecciona esta opción, es preciso que especifique un **Id. de autor de llamada alternativo** que aparecerá en la pantalla que contiene el Id. del autor de la llamada del destinatario.

9.  Para asociar una o más puertas de enlace RTC o troncos SIP a la ruta de voz, haga clic en **Agregar** y, a continuación, seleccione una puerta de enlace o un tronco SIP en la lista.
    

    > [!NOTE]
    > Si la implementación incluye algún servidor de mediación de Microsoft Office Communications Server 2007 R2, aparecerá también en la lista.



10. Para asociar uno o más registros de uso de RTC con la ruta de voz, haga clic en **Seleccionar** y elija un registro en la lista de registros de uso de RTC que se hayan definido para la implementación de Telefonía IP empresarial.
    

    > [!NOTE]
    > Para ver las propiedades de cada uno de los registros de uso de RTC disponibles, consulte <A href="lync-server-2013-view-pstn-usage-records.md">Ver registros de uso de la RTC en Lync Server 2013</A>.<BR>Para crear o editar registros de uso de RTC, consulte <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Crear una directiva de voz y configurar registros de uso de RTC en Lync Server 2013</A> o <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modificar una directiva de voz y configurar registros de uso de RTC en Lync Server 2013</A>.



11. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de registro en la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.
    

    > [!NOTE]
    > Al contrario de lo que sucede con las directivas de voz donde el orden en el que aparecen los registros de uso de RTC es importante, en una ruta de voz, el orden carece de importancia. Sin embargo, recomendamos ordenar la lista por frecuencia de uso, por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Lync Server recorre la lista de arriba abajo).



12. (Opcional) Escriba un valor en el campo **Introducir un número para probarlo** y haga clic en **Ir**. Los resultados de la prueba se muestran en el campo.
    

    > [!NOTE]
    > Puede guardar una ruta de voz que no haya pasado la prueba aún y volver a configurarla más adelante. Para más información, consulte <A href="lync-server-2013-test-voice-routing.md">Probar el enrutamiento de voz en Lync Server 2013</A>.



13. Haga clic en **Aceptar**.

14. En la página **Ruta**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    

    > [!NOTE]
    > Siempre que cree o modifique una ruta de voz, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio en la configuración. Para más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</A> en la documentación referente a las operaciones.



## Vea también

#### Tareas

[Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[Ver registros de uso de la RTC en Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Crear una directiva de voz y configurar registros de uso de RTC en Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Modificar una directiva de voz y configurar registros de uso de RTC en Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Otros recursos

[Probar el enrutamiento de voz en Lync Server 2013](lync-server-2013-test-voice-routing.md)

