---
title: Uso de la autenticación en dos fases con un cliente de Lync
TOCTitle: Uso de la autenticación en dos fases con un cliente de Lync
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn338071(v=OCS.15)
ms:contentKeyID: 56271361
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Uso de la autenticación en dos fases con un cliente de Lync

 

_**Última modificación del tema:** 2015-03-09_

En este tema se describe cómo aprovechar la autenticación en dos fases con un cliente Lync 2013.

## Iniciar sesión en Lync 2013 por primera vez

Normalmente, la información de inicio de sesión de Lync se configura automáticamente cuando se instala Lync 2013. Pero la primera vez que se usa Lync, puede que deba iniciar el cliente manualmente.

**Iniciar sesión en Lync por primera vez**

1.  Inicie sesión en la red de su organización.

2.  Seleccione **Iniciar** \> **Todos los programas** \> **Microsoft Lync \> Lync 2013**.
    
    Aparecerá la pantalla de inicio de sesión de Lync.
    
      - Si el cuadro de dirección para inicio de sesión ya está rellenado, confirme que la dirección que aparece es correcta.
    
      - Si no es correcta, o si el cuadro está vacío, escriba su dirección de inicio de sesión en Lync (generalmente es la misma que su dirección de correo electrónico).
    
      - Si aparece un cuadro de contraseña vacío, escriba su contraseña.

3.  Seleccione **Iniciar sesión**.

## Cerrar sesión en Lync

Cuando haya terminado de usar Lync, podrá cerrar la pantalla, cerrar su sesión o salir del programa, todo ello desde el menú Archivo. En la tabla siguiente se explican las diferencias entre estas opciones.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Opción</th>
<th>Qué hace</th>
<th>Cómo lo hago</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cerrar</p></td>
<td><p>Cierra la pantalla de Lync pero la sesión de Lync identificada con su Id. de usuario continúa ejecutándose. El motivo es poder seguir recibiendo notificaciones e interactuando con los demás.</p>
<p>Puede volver a abrir la pantalla en cualquier momento haciendo clic en el icono de Lync en la barra de tareas o en el área de notificación, en la parte inferior de la pantalla.</p></td>
<td><p>En la pantalla principal de Lync, haga lo siguiente:</p>
<ol>
<li><p>Seleccione el botón <strong>Opciones</strong>, luego <strong>Archivo</strong> &gt; <strong>Cerrar</strong>.</p></li>
<li><p>Haga clic en el botón <strong>Cerrar</strong> (X) situado en la esquina superior derecha de la ventana.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>Cerrar sesión</p></td>
<td><p>Finaliza la sesión de Lync asociada a su identificador de usuario, pero Lync continúa ejecutándose en segundo plano. Al cerrar la sesión, aparece la ventana de inicio de sesión.</p>
<div>

> [!TIP]  
> Seleccione <strong>Eliminar mi información de inicio de sesión</strong> al cerrar la sesión para quitar el registro de su identificador y contraseña de inicio de sesión de la memoria del equipo. De este modo debe resultar más fácil al equipo técnico ayudar a los usuarios a resolver problemas de inicio de sesión. También puede ayudar a garantizar que la información de inicio de sesión es más segura, ya que resulta más difícil para los usuarios no autorizados iniciar sesión con credenciales ajenas.


</div></td>
<td><p>En la ventana principal de Lync, seleccione el botón <strong>Opciones</strong>, luego <strong>Archivo</strong> &gt; <strong>Cerrar sesión</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>Salir</p></td>
<td><p>Finaliza su sesión de Lync y cierra Lync en su equipo. Después de haber salido, si desea volver a iniciar Lync, seleccione <strong>Inicio</strong> &gt; <strong>Todos los programas</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</p></td>
<td><p>En la ventana principal de Lync, seleccione el botón <strong>Opciones</strong>, <strong>Archivo</strong> &gt; <strong>Salir</strong>.</p></td>
</tr>
</tbody>
</table>


## Iniciar sesión en Lync con una tarjeta inteligente

En algunas organizaciones se usan un proceso de inicio de sesión de varios pasos, llamado autenticación en dos fases, para aumentar la seguridad para los usuarios de Lync 2013. Si debe usar esta opción, necesitará una “tarjeta inteligente” para iniciar sesión en Lync. Existen dos tipos de tarjetas inteligentes, las físicas y las virtuales:

  - **Física:** tiene el tamaño aproximado de una tarjeta de crédito. Se inserta en un lector al iniciar sesión.

  - **Virtual:** no es un objeto físico, sino un identificador electrónico que se copia a un chip especial en el equipo, con lo cual se genera una tarjeta virtual en el equipo. Está disponible para ser usada solo con equipos de Windows 8 que contienen el chip TPM (Módulo de plataforma segura).

## Inscriba su tarjeta inteligente

Para poder iniciar sesión con una tarjeta inteligente, esta debe primero "inscribirse", es decir, las credenciales del usuario deben identificarse con la tarjeta. Esto se aplica tanto a tarjetas físicas como virtuales. Puede que el administrador de Lync Server ya haya realizado este proceso. Compruébelo si no está seguro.


> [!NOTE]
> Dado que cada tarjeta inteligente se asocia solo al dispositivo en el que se la instala, será necesario inscribir otra tarjeta para cada equipo Windows 8 que use.



**Inscribir una tarjeta inteligente manualmente**

1.  Inicie sesión en el equipo en que se ejecutará Lync.

2.  En Internet Explorer, busque la página de inscripción web de la entidad de certificación de la organización.
    
    Si aún no la tiene, solicite la dirección web de este recurso al administrador de Lync Server. La URL será similar a: https://MiCA.\[nombredesuempresa\].com/certsrv.
    

    > [!NOTE]
    > Si usa Internet Explorer 10, puede que deba visualizar este sitio web en modo de compatibilidad.



3.  Cuando se le solicite que inicie sesión en la página de certificación, inicie sesión con la cuenta de dominio (en lugar de hacerlo como administrador del equipo).

4.  En la página principal del sitio web, seleccione **Solicitar un certificado**.

5.  Seleccione **Solicitud avanzada**.

6.  Seleccione **Crear y enviar una solicitud a esta CA** y haga clic en **Siguiente**.

7.  Aparecerá una página llamada Estación de inscripción de tarjetas inteligentes. Apruebe la solicitud para instalar el control ActiveX y luego complete el formulario Solicitud de certificado avanzada de la siguiente manera:
    
    1.  Seleccione **Usuario de tarjeta inteligente** de la lista desplegable **Plantilla de certificado**.
    
    2.  Seleccione **Crear conjunto de claves nuevo**.
    
    3.  Busque la información del fabricante en la etiqueta de la tarjeta inteligente y seleccione el fabricante de la lista desplegable **CSP**.
    
    4.  Seleccione **CSP** como el formato de la solicitud, si aún no está seleccionado.
    
    5.  Seleccione **sha1** de la lista desplegable Algoritmo hash , si aún no está seleccionado.
    
    6.  Elija un nombre que pueda reconocer para el certificado y haga clic en **Enviar**.

8.  Inserte la tarjeta inteligente vacía en el lector de tarjetas junto a la estación de inscripción y haga clic en **Inscribir**.

9.  Cuando se le indique, escriba su número de identificación personal (PIN) y haga clic en **Aceptar**.
    

    > [!NOTE]
    > Si el representante de soporte técnico no le asignó un PIN especial para usar en la inscripción de la tarjeta inteligente, use el valor de PIN predeterminado de la tarjeta, que es 12345678.



10. Seleccione la opción para forzar al usuario (usted) a que cambie el PIN la primera vez que use la tarjeta inteligente.

11. Inserte la tarjeta inteligente vacía en el lector de tarjetas junto a la estación de inscripción y haga clic en **Inscribir**.

12. Cuando se le indique, escriba su número de identificación personal (PIN) y haga clic en **Aceptar**.
    

    > [!NOTE]
    > Si el representante de soporte técnico no le asignó un PIN especial para usar en la inscripción de la tarjeta inteligente, use el valor de PIN predeterminado de la tarjeta, que es 12345678.



13. Seleccione la opción para forzar al usuario (usted) a que cambie el PIN la primera vez que use la tarjeta inteligente.

14. Haga clic en **Aceptar** para confirmar que el certificado que aparece incluye la información correspondiente.

15. Cuando vea la notificación de que se emitió el certificado, haga clic en **Instalar este certificado** para completar el proceso de inscripción.

## Iniciar sesión en Lync con las credenciales de la tarjeta inteligente

Antes de usar la tarjeta inteligente por primera vez, se recomienda que haga clic en **Eliminar info. de inicio de sesión** en la página de inicio de sesión de Lync. De este modo se borran todas las credenciales de inicio de sesión del equipo y se elimina una posible fuente de error.

**Iniciar sesión en Lync con las credenciales de la tarjeta inteligente**

1.  Inicie el cliente Lync.

2.  En la pantalla de inicio de sesión, escriba el nombre de la cuenta de usuario para iniciar la sesión en el cuadro **Dirección de inicio de sesión** y haga clic en **Iniciar sesión**.

3.  Si usa una tarjeta inteligente virtual, omita este paso.
    
    Si usa una tarjeta inteligente física, inserte la tarjeta en el lector de tarjetas inteligentes y, si se lo solicitan, haga clic en **Aceptar** cuando la tarjeta es detectada.

4.  Escriba el número de PIN para la tarjeta inteligente y haga clic en **Aceptar**.
    

    > [!NOTE]
    > Si no se le asignó un número de PIN para la tarjeta inteligente, use el valor predeterminado, que es 12345678.


