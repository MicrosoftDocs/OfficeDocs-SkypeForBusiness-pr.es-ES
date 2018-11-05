---
title: "Lync Server 2013 : Créa. d’un cas de test de routage des comm. vocales"
TOCTitle: Crear un caso de prueba de enrutamiento de voz
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48275118
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear un caso de prueba de enrutamiento de voz en Lync Server 2013

 

_**Última modificación del tema:** 2014-02-07_

## Para crear un caso de prueba

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Probar enrutamiento de voz**.

4.  En la página **Probar enrutamiento de voz**, haga clic en **Nuevo** para crear un nuevo caso de prueba.

5.  En **Nombre**, escriba un nombre único para el caso de prueba.
    
    El nombre debe ser distinto al resto de casos de prueba de enrutamientos de voz de la implementación de Telefonía IP empresarial. Puede tener una longitud de hasta 32 caracteres y contener caracteres alfanuméricos, además de barras diagonales inversas (\\), puntos (.) o caracteres de subrayado (\_).

6.  En **Número marcado para prueba**, escriba el número marcado que desea usar para probar la configuración de enrutamiento especificada para este caso de prueba. Según el plan de marcado, la ruta y la directiva de voz, este número se normalizará y se mostrará como resultado.

7.  En la lista **Plan de marcado**, seleccione el plan de marcado que se va a usar cuando se ejecute la prueba. El plan de marcado predeterminado es el plan de marcado Global.

8.  En la lista **Directiva de voz**, seleccione la directiva de voz que se va a usar cuando se ejecute la prueba. La directiva de voz predeterminada es la directiva de voz Global.

9.  En **Conversión prevista**, escriba el número de teléfono en el formato que desea que se muestre tras la conversión. Dicho número corresponde al valor del número de teléfono que se está probando tras la conversión de la primera regla de normalización que coincida con el plan de marcado seleccionado. Cuando ejecuta el caso de prueba, sabrá si ha fallo cuando el número que se está probando no se convierte en el valor especificado en **Conversión prevista**.

10. (Opcional) En la lista **Uso de RTC previsto**, puede seleccionar el registro de uso de la red telefónica conmutada (RTC) que espera que se use al ejecutar el caso de prueba, según el plan de marcado y la directiva de voz que se han especificado. Si se usa un registro de uso de RTC diferente significa que la prueba ha fallado.

11. (Opcional) En la lista **Ruta prevista**, puede seleccionar la ruta de voz que espera que se use al ejecutar el caso de prueba, según el plan de marcado y la directiva de voz que se han especificado. Si se usa una ruta de voz diferente significa que la prueba ha fallado.

12. (Opcional) Haga clic en **Ejecutar** para iniciar el caso de prueba. Los resultados se mostrarán en el panel que hay a la derecha de la página.

13. Haga clic en **Aceptar**.

14. Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    

    > [!NOTE]
    > Siempre que cree un caso de prueba de enrutamiento de voz, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración. Para información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</A> en la documentación sobre operaciones.

    
    Si el plan de marcado que se está utilizando en la prueba normaliza los números de teléfono que comienzan con el signo más (como, por ejemplo, +12065551219), ese plan podría provocar que la prueba de enrutamiento de voz fallara. (El plan de marcado y la ruta de voz funcionarán. De hecho, Test-CsDialPlan concluirá con éxito. Sin embargo, la prueba de enrutamiento podría fallar.) Recuerde esta advertencia cuando realice pruebas de enrutamiento de voz.

## Vea también

#### Tareas

[Exportar casos de prueba de enrutamiento de voz en Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
[Importar casos de prueba de enrutamiento de voz en Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  

#### Otros recursos

[Configurar planes de marcado en Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Configuración de directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

