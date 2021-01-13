---
title: Usar la autenticación en dos fases con el cliente de Skype Empresarial y Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 'Resumen: use la autenticación en dos fases con Skype Empresarial Server y Skype Empresarial.'
ms.openlocfilehash: 72ec3570d632eecefd28ebfd0aa50eb70c54ff99
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806549"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Usar la autenticación en dos fases con el cliente de Skype Empresarial y Skype Empresarial Server
 
**Resumen:** Use la autenticación en dos fases con Skype Empresarial Server y Skype Empresarial.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Iniciar sesión en Skype Empresarial por primera vez

La información de inicio de sesión suele configurarse automáticamente cuando se instala Skype Empresarial. Pero la primera vez que use Skype Empresarial, es posible que tenga que iniciar manualmente el cliente.
  
### <a name="to-sign-in-for-the-first-time"></a>Para iniciar sesión por primera vez

1. Inicie sesión en la red de su organización.
    
2. Seleccione **Iniciar todos** los  >  **programas** skype  >  **empresarial.**
    
    Debería ver la pantalla de inicio de sesión.
    
    - Si el cuadro de dirección de inicio de sesión ya está lleno, confirme que la dirección que se muestra es correcta.
    
    - Si no es correcto o si el cuadro está vacío, escriba la dirección de inicio de sesión (normalmente es la misma que la dirección de correo electrónico).
    
    - Si se muestra un cuadro de contraseña vacío, agregue la contraseña.
    
3. Seleccione **Iniciar sesión.**
    
## <a name="sign-out-of-skype-for-business"></a>Cerrar sesión en Skype Empresarial

Cuando haya terminado de usar Skype Empresarial, puede cerrar la pantalla, cerrar la sesión o salir del programa, todo desde el menú Archivo. En la tabla siguiente se explican las diferencias entre las opciones.
  
|**Opción**|**Lo que hace**|**Cómo realizarlo**|
|:-----|:-----|:-----|
|Cerrar  <br/> |Cierra la pantalla, pero permite que la sesión de Skype Empresarial identificada con su id. de usuario continúe funcionando. Esto es para que puedas seguir recibiendo notificaciones e interactuar con otros usuarios. <br/> <br/> Puede volver a mostrar la pantalla en cualquier momento haciendo clic en el icono de Skype Empresarial en la barra de tareas o en el área de notificación en la parte inferior de la pantalla.  <br/> | En la ventana principal de Skype Empresarial, realice una de las siguientes acciones: <br/> 1. Seleccione el botón **Opciones** y, a continuación, seleccione **Cerrar**  >  **archivo.**  <br/> 2. Haga clic en **el botón** Cerrar (X) en la esquina superior derecha de la ventana. <br/> |
|Cerrar sesión  <br/> |Finaliza la sesión asociada con su identificador de usuario, pero Skype Empresarial sigue en ejecución en segundo plano. Al cerrar sesión, aparecerá la ventana de inicio de sesión.  <br/> **Sugerencia:** Seleccione **Eliminar mi información de inicio de** sesión cuando cierre la sesión para quitar del equipo el registro del identificador de inicio de sesión y la contraseña. Esto puede facilitar a los usuarios de soporte técnico la solución de problemas de inicio de sesión. También puede ayudar a garantizar que la información de inicio de sesión sea más segura al dificultar que los usuarios no autorizados inicien sesión con sus credenciales. <br/> |En la ventana principal de Skype Empresarial, seleccione **el** botón Opciones y, a continuación, **seleccione Cerrar** sesión en  >  **el archivo.**  <br/> |
|Salir  <br/> |Finaliza la sesión de Skype Empresarial y cierra Skype Empresarial en su equipo. Después de salir, si desea reiniciar, seleccione **Iniciar** todos los  >   programas > Skype Empresarial. <br/> |En la ventana principal de Skype Empresarial, seleccione **el** botón Opciones y, a continuación, seleccione **Salir**  >  **de archivo.**  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Iniciar sesión en Skype Empresarial con una tarjeta inteligente

Algunas organizaciones ahora usan un proceso de inicio de sesión en varios pasos, denominado autenticación en dos fases, para aumentar la seguridad de sus usuarios. Si se espera que use esta opción, necesitará una "tarjeta inteligente" para iniciar sesión en Skype Empresarial. Las tarjetas inteligentes pueden ser físicas o virtuales:
  
- **Físico** Acerca del tamaño de una tarjeta de crédito. Se inserta en un lector de tarjetas inteligentes al iniciar sesión.
    
- **Virtual** No es un objeto físico, sino un identificador electrónico que se escribe en un chip especial del equipo, que en esencia crea la tarjeta inteligente en el equipo. Solo está disponible para su uso con equipos con Windows 8 que contienen el chip TPM (Módulo de plataforma segura).
    
### <a name="enroll-your-smart-card"></a>Inscribir la tarjeta inteligente

Para poder iniciar sesión con una tarjeta inteligente, la tarjeta debe estar "inscrita", es decir, las credenciales de usuario deben identificarse con la tarjeta. Este es el caso si la tarjeta es física o virtual. Es posible que el administrador de Skype Empresarial Server ya haya llevado a cabo este proceso. Consulte con ellos si no está seguro de si se ha realizado.
  
> [!NOTE]
> Dado que cada tarjeta inteligente virtual está asociada solo con el dispositivo en el que está instalada, tendrá que inscribirse una tarjeta independiente para cada equipo con Windows 8 que use. 
  
### <a name="to-manually-enroll-your-smart-card"></a>Para inscribir manualmente la tarjeta inteligente

1. Inicie sesión en el equipo en el que va a ejecutar Skype Empresarial.
    
2. Con Internet Explorer, vaya a la página de inscripción web de entidad de certificación de su organización. 
    
    Pida a su administrador de Skype Empresarial Server la dirección web de este recurso si aún no la tiene. La dirección URL tendrá un aspecto parecido al siguiente: https://MyCA .[ yourcompanyname].com/certsrv.
    
    > [!NOTE]
    > Si usas Internet Explorer 10, es posible que debas ver este sitio web en modo de compatibilidad. 
  
3. Cuando se le pida que inicie sesión en la página de certificación, inicie sesión con su cuenta de dominio (en lugar de como administrador del equipo).
    
4. En la página principal del sitio web, seleccione **Solicitar un certificado.**
    
5. Seleccione **Solicitud avanzada.**
    
6. Seleccione **Crear y enviar una solicitud a esta CA** y, a continuación, haga clic en **Siguiente.**
    
7. Ahora verás una página denominada Estación de inscripción de tarjeta inteligente. Apruebe la solicitud para instalar el control ActiveX y, a continuación, complete el formulario solicitud de certificado avanzada de la siguiente manera:
    
    a. Selecciona **usuario de tarjeta inteligente en** la lista desplegable **Plantilla** de certificado.
    
    b. Seleccione **Crear nuevo conjunto de claves.**
    
    c. Busca la información del fabricante en la etiqueta de la tarjeta inteligente y selecciona ese fabricante en la lista desplegable **de CSP.**
    
    d. Selecciona **CSP** como formato de solicitud, si aún no está seleccionado.
    
    e. Seleccione **sha1** en la lista desplegable Algoritmo hash, si aún no está seleccionado.
    
    f. Asigne a su certificado un nombre que reconocerá y haga clic en **Enviar.**
    
8. Ahora inserta la tarjeta inteligente en blanco en el lector de tarjetas adjunto a la estación de inscripción y haz clic en **Inscribir.**
    
9. Cuando se le solicite, escriba su número de identificación personal (PIN) y, a continuación, haga clic en **Aceptar.**
    
    > [!NOTE]
    > Si la persona de soporte técnico no le ha dado un PIN especial para inscribir la tarjeta inteligente, use el valor de PIN predeterminado de la tarjeta inteligente, que es 12345678. 
  
10. Seleccione la opción para forzar al usuario (usted) a cambiar el PIN la primera vez que se usa la tarjeta inteligente.
    
11. Ahora inserta la tarjeta inteligente en blanco en el lector de tarjetas adjunto a la estación de inscripción y haz clic en **Inscribir.**
    
12. Cuando se le solicite, escriba su número de identificación personal (PIN) y, a continuación, haga clic en **Aceptar.**
    
    > [!NOTE]
    > Si la persona de soporte técnico no le ha dado un PIN especial para inscribir la tarjeta inteligente, use el valor de PIN predeterminado de la tarjeta inteligente, que es 12345678. 
  
13. Seleccione la opción para forzar al usuario (usted) a cambiar el PIN la primera vez que se usa la tarjeta inteligente.
    
14. Haga **clic en** Aceptar para confirmar que el certificado mostrado tiene su información.
    
15. Una vez que veas el aviso de que se ha emitido el certificado, haz clic en Instalar **este certificado** para completar el proceso de inscripción.
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Iniciar sesión en Skype Empresarial con sus credenciales de tarjeta inteligente

Antes de usar la tarjeta inteligente por primera vez,  se recomienda que haga clic en Eliminar mi información de inicio de sesión en la página de inicio de sesión de Skype Empresarial. Al hacerlo, se borran las credenciales de inicio de sesión almacenadas en el equipo y se elimina un posible origen de errores.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Para iniciar sesión en Skype Empresarial con sus credenciales de tarjeta inteligente

1. Inicie el cliente de Skype Empresarial.
    
2. En la pantalla Inicio de sesión, escriba  el nombre de la cuenta de usuario de inicio de sesión en el cuadro Dirección de inicio de sesión y, a continuación, haga clic **en Iniciar sesión.**
    
3. Si usa una tarjeta inteligente virtual, omita este paso.
    
    Si usa una tarjeta inteligente física, inserte la tarjeta inteligente en el lector de  tarjetas inteligentes y se le pedirá que lo haga y, a continuación, haga clic en Aceptar cuando se detecte la tarjeta.
    
4. Escriba el número PIN que necesita para la tarjeta inteligente y, a continuación, haga clic en **Aceptar.**
    
    > [!NOTE]
    > Si la persona de soporte técnico no le asignó un número de PIN de tarjeta inteligente, use el valor predeterminado, que es 12345678. 
  
## <a name="see-also"></a>Vea también

[Administrar la autenticación en dos fases en Skype Empresarial Server](two-factor-authentication.md)
  
[Configurar la autenticación en dos fases en Skype Empresarial Server](configure-two-factor.md)
