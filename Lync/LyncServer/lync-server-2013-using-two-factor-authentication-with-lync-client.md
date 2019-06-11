---
title: 'Lync Server 2013: uso de la autenticación en dos fases con el cliente de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5af9e9b5268fd218bfe5856473124514cfe34945
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a>Usar la autenticación en dos fases con el cliente de Lync y Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-11_

En este tema se describe cómo aprovechar la autenticación en dos fases con el cliente de Lync 2013.

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a>Iniciar sesión en Lync 2013 por primera vez

La información de inicio de sesión de Lync se suele configurar automáticamente cuando Lync 2013 está instalado. Pero la primera vez que usa Lync, es posible que tenga que iniciar el cliente de forma manual.

**Para iniciar sesión en Lync por primera vez**

1.  Inicie sesión en la red de su organización.

2.  Seleccione **iniciar** \> **todos los programas** \> **Microsoft \> Lync Lync 2013**.
    
    Debería ver la pantalla de inicio de sesión de Lync.
    
      - Si el cuadro de dirección para inicio de sesión ya está rellenado, confirme que la dirección que aparece es correcta.
    
      - Si no es correcta, o si el cuadro está vacío, escriba su dirección de inicio de sesión de Lync (normalmente es la misma que su dirección de correo electrónico).
    
      - Si aparece un cuadro de contraseña vacío, escriba su contraseña.

3.  Seleccione **Iniciar sesión**.

</div>

<div>

## <a name="sign-out-of-lync"></a>Cerrar la sesión de Lync

Cuando haya terminado de usar Lync, puede cerrar la pantalla, cerrar la sesión de la sesión o salir del programa, todo desde el menú archivo. En la tabla siguiente se explican las diferencias entre estas opciones.


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
<td><p>Cierra la pantalla de Lync, pero permite que la sesión de Lync identificada con su identificador de usuario continúe ejecutándose. El motivo es poder seguir recibiendo notificaciones e interactuando con los demás.</p>
<p>Puede volver a abrir la pantalla en cualquier momento haciendo clic en el icono de Lync en la barra de tareas o en el área de notificación de la parte inferior de la pantalla.</p></td>
<td><p>En la ventana principal de Lync, siga uno de estos procedimientos:</p>
<ol>
<li><p>Seleccione el <strong>botón Opciones</strong> y, a continuación, haga clic en <strong>cerrar</strong> <strong>archivo</strong> &gt; .</p></li>
<li><p>Haga clic en el botón <strong>Cerrar</strong> (X) situado en la esquina superior derecha de la ventana.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>Cerrar sesión</p></td>
<td><p>Finaliza la sesión de Lync asociada a su identificador de usuario, pero Lync continúa ejecutándose en segundo plano. Al cerrar la sesión, aparece la ventana de inicio de sesión.</p>
<div>

> [!TIP]  
> Seleccione <STRONG>Eliminar mi información de inicio de sesión</STRONG> al cerrar la sesión para quitar el registro de su identificador y contraseña de inicio de sesión de la memoria del equipo. De este modo tiene que resultar más fácil al equipo técnico ayudar a los usuarios a resolver problemas de inicio de sesión. También puede ayudar a garantizar que la información de inicio de sesión es más segura, ya que resulta más difícil para los usuarios no autorizados iniciar sesión con credenciales ajenas.


</div></td>
<td><p>En la ventana principal de Lync, seleccione el botón <strong>Opciones</strong> y, a continuación, seleccione <strong>Cerrar sesión</strong>en <strong>archivo</strong> &gt; .</p></td>
</tr>
<tr class="odd">
<td><p>Salir</p></td>
<td><p>Finaliza la sesión de Lync y cierra Lync en el equipo. Después de haber salido, si quiere reiniciar Lync, seleccione <strong>iniciar</strong> &gt; <strong>todos los programas</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</p></td>
<td><p>En la ventana principal de Lync, seleccione el botón <strong>Opciones</strong> y, a continuación, seleccione <strong>salida</strong>de <strong>archivo</strong> &gt; .</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a>Iniciar sesión en Lync con una tarjeta inteligente

Algunas organizaciones ahora usan un proceso de inicio de sesión de varios pasos, denominado autenticación en dos fases, para aumentar la seguridad de los usuarios de Lync 2013. Si tiene previsto usar esta opción, necesitará una "tarjeta inteligente" para iniciar sesión en Lync. Las tarjetas inteligentes vienen en dos variedades, físicas y virtuales:

  - **Físico**   sobre el tamaño de una tarjeta de crédito. Se inserta en un lector al iniciar sesión.

  - **Virtual**   no es un objeto físico, sino un identificador electrónico que se escribe en un chip especial de su equipo, que, en esencia, crea la tarjeta inteligente en el equipo. Solo disponible para usar con equipos con Windows 8 que contengan el chip TPM (módulo de plataforma segura).

<div>

## <a name="enroll-your-smart-card"></a>Inscriba su tarjeta inteligente

Para poder iniciar sesión con una tarjeta inteligente, esta necesita primero "inscribirse", es decir, las credenciales del usuario tienen que identificarse con la tarjeta. Esto se aplica tanto a tarjetas físicas como virtuales. Es posible que el administrador de Lync Server ya haya realizado este proceso. Compruébelo si no está seguro.

<div>


> [!NOTE]  
> Como cada tarjeta inteligente virtual solo está asociada con el dispositivo en el que está instalada, será necesario inscribir una tarjeta independiente para cada equipo con Windows 8 que use.



</div>

**Inscribir una tarjeta inteligente manualmente**

1.  Inicie sesión en el equipo en el que va a ejecutar Lync.

2.  En Internet Explorer, busque la página de inscripción web de la entidad de certificación de la organización.
    
    Pida a su administrador de Lync Server la dirección Web de este recurso si aún no la tiene. La dirección URL tendrá un aspecto similar a https://MyCA.\este:\][elnombredesuempresa. com/certsrv.
    
    <div>
    

    > [!NOTE]  
    > Si usa Internet Explorer 10, puede que tenga que visualizar este sitio web en modo de compatibilidad.

    
    </div>

3.  Cuando se le solicite que inicie sesión en la página de certificación, inicie sesión con la cuenta de dominio (en lugar de hacerlo como administrador del equipo).

4.  En la página principal del sitio web, seleccione **Solicitar un certificado**.

5.  Seleccione **Solicitud avanzada**.

6.  Seleccione **Crear y enviar una solicitud a esta CA** y haga clic en **Siguiente**.

7.  Aparecerá una página llamada Estación de inscripción de tarjetas inteligentes. Apruebe la solicitud para instalar el control ActiveX y luego complete el formulario Solicitud de certificado avanzada de la siguiente manera:
    
    1.  Seleccione **Usuario de tarjeta inteligente** de la lista desplegable **Plantilla de certificado**.
    
    2.  Seleccione **Crear conjunto de claves nuevo**.
    
    3.  Busque la información del fabricante en la etiqueta de la tarjeta inteligente y seleccione el fabricante de la lista desplegable **CSP**.
    
    4.  Seleccione **CSP** como el formato de la solicitud, si aún no está seleccionado.
    
    5.  Seleccione **sha1** de la lista desplegable Algoritmo hash, si aún no está seleccionado.
    
    6.  Elija un nombre que pueda reconocer para el certificado y haga clic en **Enviar**.

8.  Inserte la tarjeta inteligente vacía en el lector de tarjetas junto a la estación de inscripción y haga clic en **Inscribir**.

9.  Cuando se le indique, escriba su número de identificación personal (PIN) y haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Si el representante de soporte técnico no le asignó un PIN especial para usar en la inscripción de la tarjeta inteligente, use el valor de PIN predeterminado de la tarjeta, que es 12345678.

    
    </div>

10. Seleccione la opción para forzar al usuario (usted) a que cambie el PIN la primera vez que use la tarjeta inteligente.

11. Inserte la tarjeta inteligente vacía en el lector de tarjetas junto a la estación de inscripción y haga clic en **Inscribir**.

12. Cuando se le indique, escriba su número de identificación personal (PIN) y haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Si el representante de soporte técnico no le asignó un PIN especial para usar en la inscripción de la tarjeta inteligente, use el valor de PIN predeterminado de la tarjeta, que es 12345678.

    
    </div>

13. Seleccione la opción para forzar al usuario (usted) a que cambie el PIN la primera vez que use la tarjeta inteligente.

14. Haga clic en **Aceptar** para confirmar que el certificado que aparece incluye la información correspondiente.

15. Cuando vea la notificación de que se emitió el certificado, haga clic en **Instalar este certificado** para completar el proceso de inscripción.

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a>Iniciar sesión en Lync con las credenciales de su tarjeta inteligente

Antes de usar su tarjeta inteligente por primera vez, le recomendamos que haga clic en **eliminar mi información de inicio de sesión** en la página de inicio de sesión de Lync. De esta manera, se borran todas las credenciales de inicio de sesión almacenadas en el equipo y se elimina una posible fuente de error.

**Para iniciar sesión en Lync con las credenciales de su tarjeta inteligente**

1.  Inicie el cliente de Lync.

2.  En la pantalla de inicio de sesión, escriba el nombre de la cuenta de usuario para iniciar la sesión en el cuadro **Dirección de inicio de sesión** y haga clic en **Iniciar sesión**.

3.  Si usa una tarjeta inteligente virtual, omita este paso.
    
    Si usa una tarjeta inteligente física, inserte la tarjeta en el lector de tarjetas inteligentes y, si se lo solicitan, haga clic en **Aceptar** cuando la tarjeta es detectada.

4.  Escriba el número de PIN para la tarjeta inteligente y haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Si no se le asignó un número de PIN para la tarjeta inteligente, use el valor predeterminado, que es 12345678.

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

