---
title: 'Lync Server 2013: usar la autenticación en dos fases con el cliente de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c90183d13581387d444301278d4c1c1125e5dc91
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a>Uso de la autenticación en dos fases con Lync Client y Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-11_

En este tema se describió cómo aprovechar la autenticación en dos fases con el cliente de Lync 2013.

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a>Iniciar sesión en Lync 2013 por primera vez

La información de inicio de sesión de Lync suele configurarse automáticamente cuando Lync 2013 está instalado. Pero la primera vez que use Lync, es posible que deba iniciar manualmente el cliente.

**Para iniciar sesión en Lync por primera vez**

1.  Inicie sesión en la red de su organización.

2.  Seleccione **iniciar** \> **todos los programas** \> **Microsoft \> Lync Lync 2013**.
    
    Debería ver la pantalla de inicio de sesión de Lync.
    
      - Si el cuadro Dirección de inicio de sesión ya está rellenado, confirme que la dirección mostrada es correcta.
    
      - Si no es correcta o si el cuadro está vacío, escriba su dirección de inicio de sesión de Lync (normalmente es la misma que su dirección de correo electrónico).
    
      - Si se muestra un cuadro de contraseña vacío, agregue su contraseña.

3.  Seleccione **iniciar sesión**.

</div>

<div>

## <a name="sign-out-of-lync"></a>Cerrar sesión en Lync

Cuando haya terminado de usar Lync, podrá cerrar la pantalla, cerrar la sesión de la sesión o salir del programa, todo desde el menú archivo. En la tabla siguiente se explican las diferencias de las opciones.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Opción</th>
<th>Lo que hace</th>
<th>Cómo realizarlo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cerrar</p></td>
<td><p>Cierra la presentación de Lync, pero permite que la sesión de Lync identificada con su identificador de usuario continúe ejecutándose. Esto es así para que pueda seguir recibiendo notificaciones e interactuar con otros usuarios.</p>
<p>Puede volver a mostrar la presentación en cualquier momento haciendo clic en el icono de Lync de la barra de tareas o en el área de notificación en la parte inferior de la pantalla.</p></td>
<td><p>En la ventana principal de Lync, realice una de las siguientes acciones:</p>
<ol>
<li><p>Seleccione el <strong>botón Opciones</strong> y, después, haga clic en <strong>cerrar</strong> <strong>archivo</strong> &gt; .</p></li>
<li><p>Haga clic en el botón Cerrar (X) que se <strong>incluye</strong> en la esquina superior derecha de la ventana.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>Cerrar sesión</p></td>
<td><p>Finaliza la sesión de Lync asociada con el identificador de usuario, pero Lync sigue ejecutándose en segundo plano. Cuando cierre sesión, aparecerá la ventana de inicio de sesión.</p>
<div>

> [!TIP]  
> Seleccione <STRONG>eliminar mi información</STRONG> de inicio de sesión al cerrar la sesión para quitar el registro del identificador de inicio de sesión y la contraseña del equipo. Al hacerlo, es posible que sea más fácil para los usuarios de soporte técnico solucionar problemas de inicio de sesión. También puede ayudar a garantizar que la información de inicio de sesión sea más segura, lo que dificulta que los usuarios no autorizados inicien sesión con sus credenciales.


</div></td>
<td><p>En la ventana principal de Lync, seleccione el botón <strong>Opciones</strong> y, después, seleccione <strong>Cerrar sesión</strong>en el <strong>archivo</strong> &gt; .</p></td>
</tr>
<tr class="odd">
<td><p>Salir</p></td>
<td><p>Finaliza la sesión de Lync y cierra Lync en el equipo. Después de salir, si quiere reiniciar Lync, seleccione <strong>iniciar</strong> &gt; <strong>todos los programas</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</p></td>
<td><p>En la ventana principal de Lync, seleccione el botón <strong>Opciones</strong> y, a continuación, seleccione <strong>salida</strong>de <strong>archivo</strong> &gt; .</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a>Iniciar sesión en Lync con una tarjeta inteligente

Algunas organizaciones ahora usan un proceso de inicio de sesión de varios pasos, denominado autenticación en dos fases, para aumentar la seguridad de los usuarios de Lync 2013. Si tiene previsto usar esta opción, necesitará una "tarjeta inteligente" para iniciar sesión en Lync. Las tarjetas inteligentes vienen en dos variedades, físicas y virtuales:

  - **Físico**   sobre el tamaño de una tarjeta de crédito. Insértelo en un lector de tarjetas inteligentes cuando inicie sesión.

  - **Virtual**   no es un objeto físico, sino un identificador electrónico que se escribe en un chip especial del equipo, que, en esencia, crea la tarjeta inteligente en el equipo. Disponible solo para usar con equipos con Windows 8 que contengan el chip TPM (módulo de plataforma segura).

<div>

## <a name="enroll-your-smart-card"></a>Inscriba su tarjeta inteligente

Para poder iniciar sesión con una tarjeta inteligente, la tarjeta debe estar "inscrito"; es decir, las credenciales de usuario deben identificarse con la tarjeta. Este es el caso si la tarjeta es física o virtual. Es posible que este proceso ya lo haya realizado el administrador de Lync Server. Compárelas si no está seguro de si se ha hecho.

<div>


> [!NOTE]  
> Como cada tarjeta inteligente virtual solo está asociada con el dispositivo en el que está instalada, será necesario inscribir una tarjeta independiente para cada equipo con Windows 8 que use.



</div>

**Para inscribir manualmente su tarjeta inteligente**

1.  Inicie sesión en el equipo en el que va a ejecutar Lync.

2.  Con Internet Explorer, vaya a la página de inscripción Web de la entidad de certificación de la organización.
    
    Solicite a su administrador de Lync Server la dirección Web de este recurso si todavía no la tiene. La dirección URL tendrá un aspecto similar a https://MyCA.\este:\][nombredesuempresa. com/certsrv.
    
    <div>
    

    > [!NOTE]  
    > Si usa Internet Explorer 10, es posible que deba ver este sitio web en modo de compatibilidad.

    
    </div>

3.  Cuando se le solicite que inicie sesión en la página de certificación, inicie sesión con su cuenta de dominio (en lugar de hacerlo como administrador del equipo).

4.  En la página de bienvenida del sitio web, seleccione **solicitar un certificado**.

5.  Seleccione **solicitud avanzada**.

6.  Seleccione **crear y enviar una solicitud a esta CA**y, a continuación, haga clic en **siguiente**.

7.  Ahora verá una página denominada estación de inscripción para tarjetas inteligentes. Apruebe la solicitud para instalar el control ActiveX y, a continuación, complete el formulario de solicitud de certificado avanzado de la siguiente manera:
    
    1.  Seleccione **usuario de tarjeta inteligente** en la lista desplegable **plantilla de certificado** .
    
    2.  Seleccione **crear conjunto de claves nuevo**.
    
    3.  Busque la información del fabricante en la etiqueta de la tarjeta inteligente y seleccione ese fabricante en la lista desplegable **CSP** .
    
    4.  Seleccione **CSP** como el formato de solicitud, si aún no está seleccionado.
    
    5.  Seleccione **SHA1** en la lista desplegable algoritmo hash, si aún no está seleccionado.
    
    6.  Asigne un nombre al certificado que reconozca y haga clic en **Enviar**.

8.  Ahora, inserte la tarjeta inteligente en blanco en el lector de tarjetas conectado a la estación de inscripción y haga clic en **inscribirse**.

9.  Cuando se le solicite, escriba su número de identificación personal (PIN) y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Si el personal de soporte técnico no le ha proporcionado un PIN especial para suscribirse a la tarjeta inteligente, use el valor predeterminado de PIN de la tarjeta inteligente, que es 12345678.

    
    </div>

10. Seleccione la opción para forzar al usuario (usted) a cambiar el PIN la primera vez que se use la tarjeta inteligente.

11. Ahora, inserte la tarjeta inteligente en blanco en el lector de tarjetas conectado a la estación de inscripción y haga clic en **inscribirse**.

12. Cuando se le solicite, escriba su número de identificación personal (PIN) y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Si el personal de soporte técnico no le ha proporcionado un PIN especial para suscribirse a la tarjeta inteligente, use el valor predeterminado de PIN de la tarjeta inteligente, que es 12345678.

    
    </div>

13. Seleccione la opción para forzar al usuario (usted) a cambiar el PIN la primera vez que se use la tarjeta inteligente.

14. Haga clic en **Aceptar** para confirmar que el certificado que se muestra contiene su información.

15. Una vez que vea el aviso de que se ha emitido el certificado, haga clic en **instalar este certificado** para completar el proceso de inscripción.

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a>Iniciar sesión en Lync con las credenciales de la tarjeta inteligente

Antes de usar la tarjeta inteligente por primera vez, se recomienda que haga clic en **eliminar mi información de inicio de sesión** en la página de inicio de sesión de Lync. De esta manera, se borran las credenciales de inicio de sesión almacenadas en el equipo y se elimina un posible origen de error.

**Para iniciar sesión en Lync con las credenciales de la tarjeta inteligente**

1.  Inicie el cliente de Lync.

2.  En la pantalla de inicio de sesión, escriba el nombre de la cuenta de usuario de inicio de sesión en el cuadro **dirección de inicio de sesión** y, a continuación, haga clic en **iniciar sesión**.

3.  Si usa una tarjeta inteligente virtual, omita este paso.
    
    Si usa una tarjeta inteligente física, inserte la tarjeta inteligente en el lector de tarjetas inteligentes y se le pedirá que lo haga y, a continuación, haga clic en **Aceptar** cuando se detecte la tarjeta.

4.  Escriba el número de PIN de la tarjeta inteligente y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Si el personal de soporte no le asignó un número PIN de tarjeta inteligente, use el valor predeterminado, que es 12345678.

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

