﻿---
title: "Exécuter des tests informels de routage des comm. Voc. dans Lync Server 2013"
TOCTitle: "Exécuter des tests informels de routage des comm. Voc. dans Lync Server 2013"
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48277047
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ejecutar pruebas informales de enrutamiento de voz en Lync Server 2013

 

_**Última modificación del tema:** 2012-08-07_

Puede usar el cuadro de diálogo **Crear información de caso de prueba de enrutamiento de voz** para ejecutar pruebas informales antes de crear un caso de prueba real. Cuando esté satisfecho con el resultado de una prueba, dispone de la opción de guardarlo como caso de prueba formal.

## Para ejecutar una prueba de enrutamiento de voz informal

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Probar enrutamiento de voz**.

4.  En la página **Probar enrutamiento de voz**, haga clic en **Crear información de caso de prueba de enrutamiento de voz**.

5.  En el campo **Número marcado**, escriba el número de teléfono que desee usar para esta prueba. El número se normalizará y se mostrará en el campo **Número normalizado** del panel **Resultados**.

6.  En la lista **Plan de marcado**, seleccione el plan de marcado que se usará para probar el número marcado. El plan de marcado predeterminado es el plan de marcado Global.
    
    Cuando ejecute la prueba, la primera regla de normalización del plan de marcado que coincida con el número marcado aparecerá en el campo **Regla de normalización** del panel **Resultados**.

7.  En la lista **Directiva de voz**, seleccione la directiva de voz que se usará para probar el número marcado. La directiva de voz predeterminada es la directiva de voz Global.
    
    Cuando ejecute la prueba, el primer registro de uso de RTC coincidente en esta directiva de voz se mostrará en el campo **Primer uso de RTC** del panel **Resultados**. Asimismo, la primera ruta de voz coincidente que se asocie con este registro de uso de RTC se mostrará en el campo **Primera ruta**.

8.  (Opcional) Active la casilla **Rellenar con usuario** si desea probar el número marcado con la directiva de voz asignada a un usuario en concreto.
    
    1.  Haga clic en **Examinar** para mostrar el cuadro de diálogo **Seleccionar usuarios de Telefonía IP empresarial**.
    
    2.  Haga clic en **Buscar** para visualizar la lista de usuarios habilitados para Telefonía IP empresarial.
    
    3.  Haga doble clic en el nombre del usuario cuya directiva de voz asignada desee usar para esta prueba. A continuación, el campo **Directiva** se rellenará con la directiva de voz asignada al usuario seleccionado.
    
    Cuando ejecute la prueba, el primer registro de uso de RTC coincidente en esta directiva de voz se mostrará en el campo **Primer uso de RTC** del panel **Resultados**. Asimismo, la primera ruta de voz coincidente que se asocie con este registro de uso de RTC se mostrará en el campo **Primera ruta**.

9.  Haga clic en **Ejecutar** para ejecutar el caso de prueba. Los resultados se mostrarán en el panel derecho del cuadro de diálogo.

10. (Opcional) Haga clic en **Guardar como** si desea guardar la configuración de la prueba como caso de prueba formal.
    
    1.  En el campo **Nombre** del cuadro de diálogo **Guardar información de caso de prueba de enrutamiento de voz**, escriba un nombre único para el caso de prueba.
        
        El nombre debe ser distinto al resto de casos de prueba de enrutamientos de voz de la implementación de Telefonía IP empresarial. Puede tener una longitud de hasta 32 caracteres y contener caracteres alfanuméricos, además de barras diagonales inversas (\\), puntos (.) o caracteres de subrayado (\_).
    
    2.  No olvide que los demás campos del cuadro de diálogo **Guardar información de caso de prueba de enrutamiento de voz** son de solo lectura, y se rellenan automáticamente con la configuración de la prueba informal *y* sus resultados. Compruebe que es la configuración que desea guardar para el caso de prueba.
        

        > [!NOTE]
        > Los valores de los resultados de la prueba se usan para rellenar automáticamente los campos del cuadro de diálogo <STRONG>Guardar información de caso de prueba de enrutamiento de voz</STRONG>, como sigue: 
        > <UL>
        > <LI>
        > <P><STRONG>Conversión prevista</STRONG> se rellena automáticamente con el valor del campo <STRONG>Número normalizado</STRONG>.</P>
        > <LI>
        > <P><STRONG>Ruta prevista</STRONG> se rellena automáticamente con el valor del campo <STRONG>Primera ruta</STRONG>.</P>
        > <LI>
        > <P><STRONG>Registro de uso de RTC previsto</STRONG> se rellena automáticamente con el valor del campo <STRONG>Primer uso de RTC</STRONG>.</P></LI></UL>Si no se han encontrado coincidencias con estos valores durante la ejecución de la prueba, el campo correspondiente estará vacío en el cuadro de diálogo <STRONG>Guardar información de caso de prueba de enrutamiento de voz</STRONG>.

    
    3.  Haga clic en **Aceptar** para guardar el caso de prueba, o en Cancelar para volver al cuadro de diálogo **Ver información de caso de prueba de enrutamiento de voz** y seguir desarrollando la prueba antes de guardarla.

11. Haga clic en **Confirmar** y, a continuación en **Confirmar todo**.
    

    > [!NOTE]
    > Cada vez que cree un caso de prueba de enrutamiento de voz, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el caso de prueba. Para más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</A> en la documentación referente a las operaciones.



## Vea también

#### Tareas

[Crear un caso de prueba de enrutamiento de voz en Lync Server 2013](lync-server-2013-create-a-voice-routing-test-case.md)  
[Ejecutar casos de prueba de enrutamiento en Lync Server 2013](lync-server-2013-run-voice-routing-test-cases.md)  
[Exportar casos de prueba de enrutamiento de voz en Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
[Importar casos de prueba de enrutamiento de voz en Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  

#### Otros recursos

[Configurar planes de marcado en Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Configuración de directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

