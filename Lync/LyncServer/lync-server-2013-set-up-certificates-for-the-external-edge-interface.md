---
title: 'Lync Server 2013: Configurar certificados para la interfaz perimetral externa'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2cb33a91d6609f9109e6416f5688d1b2ddfb9ed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a>Configurar certificados para la interfaz perimetral externa en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

<div>


> [!IMPORTANT]  
> Cuando ejecute el Asistente para certificados, asegúrese de haber iniciado sesión con una cuenta que sea miembro de un grupo al que se le hayan asignado los permisos adecuados para el tipo de plantilla de certificado que va a usar. De forma predeterminada, una solicitud de certificado de Lync Server usará la plantilla de certificado de servidor Web. Si usa una cuenta que sea miembro del grupo RTCUniversalServerAdmins para solicitar un certificado con esta plantilla, compruebe que el grupo tiene asignados los permisos de inscripción necesarios para usar esa plantilla.



</div>

Cada servidor perimetral requiere un certificado público en la interfaz entre la red perimetral e Internet, y el nombre alternativo de asunto del certificado debe contener los nombres externos del servicio perimetral de acceso y el servicio perimetral de conferencia web totalmente nombres de dominio calificados (FQDN).

Para obtener más información sobre este y otros requisitos de certificado, consulte [requisitos de certificados para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Para obtener una lista de entidades de certificación (CA) públicas que proporcionen certificados que cumplan con los requisitos específicos para certificados de comunicaciones unificadas y que se hayan asociado con Microsoft para asegurarse de que funcionan con el Asistente para certificados de Lync Server 2013, consulte Artículo 929395 de Microsoft Knowledge base, "partners de certificados de comunicaciones unificadas para Exchange Server y para Communications [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)Server", en.

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a>Configurar certificados en las interfaces externas

Para configurar un certificado en la interfaz de borde externo en un sitio, siga los procedimientos de esta sección para hacer lo siguiente:

  - Cree la solicitud de certificado para la interfaz externa del servidor perimetral.

  - Envíe la solicitud a la entidad emisora de certificados pública.

  - Importe el certificado de la interfaz externa de cada servidor perimetral.

  - Asigne el certificado de la interfaz externa de cada servidor perimetral.

  - Si su implementación incluye varios servidores perimetrales, exporte el certificado junto con su clave privada y, a continuación, cópielo en los otros servidores perimetrales. A continuación, para cada servidor perimetral, impórtelo y asígnelo como se ha descrito anteriormente. Repita este procedimiento para cada servidor perimetral.

Puede solicitar certificados públicos directamente desde una entidad de certificación (CA) pública (como desde el sitio web de una entidad de certificación pública). Los procedimientos de esta sección usan el Asistente de certificados para la mayoría de las tareas de certificados. Si decide solicitar un certificado directamente desde una entidad de certificación pública, tendrá que modificar cada procedimiento como corresponda para solicitar, transportar e importar el certificado, así como para importar la cadena de certificados.

Cuando solicite un certificado de una entidad emisora externa, las credenciales proporcionadas deben tener derechos para solicitar un certificado de esa entidad. Cada CA tiene una directiva de seguridad que define qué credenciales (es decir, nombres de usuarios y grupos específicos) pueden solicitar, emitir, administrar o leer certificados.

Si decide usar los certificados Microsoft Management Console (MMC) para importar la cadena de certificados y el certificado, debe importarlos en el almacén de certificados para el equipo. Si los importa al almacén de certificados de usuario o servicio, el certificado no estará disponible para su asignación en el Asistente para certificados de Lync Server 2013.

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a>Para crear la solicitud de certificado para la interfaz externa del servidor perimetral

1.  En el servidor perimetral, en el Asistente para la implementación, junto al **paso 3: solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.
    
    <div>
    

    > [!NOTE]  
    > Si su organización desea admitir la conectividad de mensajería instantánea (mi) pública con AOL, no puede usar el Asistente para la implementación de Lync Server para solicitar el certificado. En su lugar, realice los pasos de la sección "para crear una solicitud de certificado para la interfaz externa del servidor perimetral para admitir la conectividad de mensajería instantánea pública con AOL" más adelante en este tema.<BR>Si tiene varios servidores perimetrales en una ubicación de un grupo, puede ejecutar el Asistente para certificados de Lync Server 2013 en cualquiera de los servidores perimetrales.

    
    </div>

2.  En la página **Tareas de certificado disponibles**, haga clic en **Crear una nueva solicitud de certificado**.

3.  En la página **solicitud de certificado** , haga clic en certificado de **borde externo**.

4.  En la página **solicitud inmediata o** demorada, active la casilla **preparar la solicitud ahora pero enviarla más tarde** .

5.  En la **Página archivo de solicitud de certificado** , escriba la ruta de acceso completa y el nombre del archivo en el que se va a guardar la solicitud (por\\ejemplo\_,\_c: CERT la Edge. cer).

6.  En la página **especificar plantilla de certificado alternativa** , para usar una plantilla distinta de la plantilla predeterminada de WebServer, seleccione la casilla **Usar plantilla de certificado alternativa para la entidad emisora de certificados seleccionada** .

7.  En la página **nombre y configuración de seguridad** , haga lo siguiente:
    
      - En **nombre descriptivo**, escriba un nombre para mostrar para el certificado.
    
      - En **longitud bit**, especifique la longitud en bits (normalmente, el valor predeterminado de **2048**).
    
      - Compruebe que la casilla **marcar clave privada de certificado como** exportable está activada.

8.  En la página información de la **organización** , escriba el nombre de la organización y la unidad organizativa (por ejemplo, una división o un departamento).

9.  En la página **información geográfica** , especifique la información de ubicación.

10. En la página **nombre de sujeto/nombres alternativos de asunto** , se muestra la información que el asistente rellenará automáticamente. Si se necesitan nombres alternativos adicionales, debe especificarlos en los dos pasos siguientes.

11. En la página **configuración del dominio SIP en la página de nombres alternativos de asunto (San)** , seleccione la casilla dominio para agregar un SIP. \<sipdomain\> entrada a la lista de nombres alternativos de asunto.

12. En la página **configurar otros nombres alternativos de asunto** , especifique los nombres alternativos adicionales que sean obligatorios.

13. En la página **solicitar Resumen** , revise la información del certificado que se va a usar para generar la solicitud.

14. Cuando termine de ejecutarse los comandos, haga lo siguiente:
    
      - Para ver el registro de la solicitud de certificado, haga clic en **Ver registro**.
    
      - Para completar la solicitud de certificado, haga clic en **siguiente**.

15. En la página **archivo de solicitud de certificado** , haga lo siguiente:
    
      - Para ver el archivo de solicitud de firma de certificado generado (CSR), haga clic en **Ver**.
    
      - Para cerrar el asistente, haga clic en **Finalizar**.

16. Copie el archivo de salida en una ubicación en la que pueda enviarlo a la entidad emisora de certificados pública.

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>Para crear una solicitud de certificado para la interfaz externa del servidor perimetral para admitir la conectividad de mensajería instantánea pública con AOL

1.  Cuando la plantilla requerida esté disponible para la CA, use el siguiente cmdlet de Windows PowerShell en el servidor perimetral para solicitar el certificado:
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    El nombre de certificado predeterminado de la plantilla proporcionada en Lync Server 2013 es servidor Web. Especifique el nombre \<\> de la plantilla únicamente si necesita usar una plantilla distinta de la predeterminada.
    
    <div>
    

    > [!NOTE]  
    > Si su organización desea admitir la conectividad de mensajería instantánea pública con AOL, debe usar Windows PowerShell en lugar del asistente de certificados para solicitar que el certificado se asigne al borde externo del servicio perimetral de acceso. Esto se debe a que la plantilla de servidor Web de Lync Server 2013 que usa el Asistente para solicitar un certificado no admite la configuración de EKU de cliente. Antes de usar Windows PowerShell para crear el certificado, el administrador de la CA debe crear e implementar una nueva plantilla que admita EKU de cliente.

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a>Para enviar una solicitud a una entidad de certificación pública

1.  Abra el archivo de salida.

2.  Copie y pegue el contenido de la solicitud de firma de certificado (CSR).

3.  Si se le solicita, especifique lo siguiente:
    
      - **Microsoft** como la plataforma de servidor.
    
      - **IIS** como la versión.
    
      - **Servidor Web** como el tipo de uso.
    
      - **Pkcs7** como formato de respuesta.

4.  Cuando la entidad emisora pública haya verificado su información, recibirá un mensaje de correo electrónico con el texto necesario para su certificado.

5.  Copie el texto del mensaje de correo electrónico y guarde el contenido en un archivo de texto (. txt) en el equipo local.

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a>Para importar el certificado de la interfaz externa del servidor perimetral

1.  Inicie sesión como miembro del grupo administradores en el mismo servidor perimetral en el que creó la solicitud de certificado.

2.  En el Asistente para la implementación, en la página **implementar servidor perimetral** , junto al **paso 3: solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.

3.  En la página **tareas de certificados disponibles** , haga clic en **importar un certificado desde un archivo. p7b, pfx o. cer**.

4.  En la página **importar certificado** , haga clic en **examinar** para buscar y seleccionar el certificado que solicitó para la interfaz externa del servidor perimetral (o bien, puede escribir la ruta de acceso completa y el nombre de archivo). Si el certificado contiene una clave privada, seleccione **archivo de certificado contiene la clave privada del certificado** y escriba la contraseña de la clave privada. Haga clic en **Siguiente**.

5.  En la página **Resumen de importación de certificado** , revise el Resumen y, a continuación, haga clic en **siguiente**.

6.  En **ejecutar comandos**, revise los resultados de la importación, haga clic en **Ver registro** para obtener más información según sea necesario y, a continuación, haga clic en **Finalizar** para completar la importación del certificado.

7.  Si está configurando un grupo de servidores perimetrales, exporte el certificado con su clave privada, tal como se describe en el procedimiento "para exportar el certificado con la clave privada para servidores perimetrales en un grupo" más adelante en este tema. Copie el archivo de certificado exportado en los otros servidores perimetrales e impórtelo en el almacén de equipos de cada servidor perimetral.

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a>Para exportar el certificado con la clave privada para servidores perimetrales en un grupo de servidores

1.  Inicie sesión como miembro del grupo administradores en el mismo servidor perimetral en el que importó el certificado.

2.  Haga clic en **Inicio**, haga clic en **Ejecutar**y escriba **MMC**.

3.  En la consola de Microsoft Management Console (MMC), haga clic en **archivo**y, a continuación, haga clic en **Agregar o quitar complemento**.

4.  En **Agregar o quitar complementos**, haga clic en **certificados**y, a continuación, haga clic en **Agregar**.

5.  En el cuadro de diálogo **certificados** , seleccione **cuenta de equipo**, haga clic en **siguiente**, seleccione **equipo local: (el equipo en el que se está ejecutando esta consola)** en **seleccionar equipo**, haga clic en **Finalizar** y, a continuación, haga clic en **Aceptar** para configuración completa de la consola de MMC.

6.  Haga doble clic en **certificados (equipo local)** para expandir los almacenes de certificados, haga doble clic en **personal**y, a continuación, haga doble clic en **certificados**.
    
    <div>
    

    > [!IMPORTANT]  
    > Si no hay certificados en el almacén personal de certificados para el equipo local, no hay ninguna clave privada asociada al certificado que se importó. Revise los pasos de la solicitud e importar. Si el problema persiste, póngase en contacto con el administrador o el proveedor de su entidad de certificación.

    
    </div>

7.  En el **almacén personal de certificados del equipo local**, haga clic con el botón secundario en el certificado que va a exportar, haga clic en **todas las tareas**y, a continuación, haga clic en **exportar**.

8.  En el Asistente para exportación de certificados, haga clic en **siguiente**, seleccione **sí, exportar la clave privada**y, a continuación, haga clic en **siguiente**.
    
    <div>
    

    > [!NOTE]  
    > Si la selección <STRONG>sí, exportar la clave privada</STRONG> no está disponible, la clave privada asociada a este certificado no se marcó para exportar. Tendrá que volver a solicitar el certificado, lo que garantiza que el certificado estará marcado para permitir la exportación de la clave privada antes de poder continuar con la exportación. Póngase en contacto con el administrador o proveedor de su entidad de certificación.

    
    </div>

9.  En el cuadro de diálogo Exportar formatos de archivo, seleccione **intercambio de\#información personal – PKCS 12 (. PFX)** y, a continuación, seleccione lo siguiente:
    
      - Incluir todos los certificados en la ruta de certificación si es posible
    
      - Exportar todas las propiedades extendidas
        
        <div>
        

        > [!WARNING]  
        > Al exportar el certificado desde un servidor perimetral, no seleccione <STRONG>eliminar la clave privada si la exportación es correcta</STRONG>. Si selecciona esta opción, necesitará importar el certificado y la clave privada a este servidor perimetral.

        
        </div>

10. Haga clic en **Siguiente**.

11. Escriba una contraseña para la clave privada, vuelva a escribir la contraseña para confirmarla y, a continuación, haga clic en **siguiente**.

12. Escriba la ruta y el nombre de archivo del certificado exportado, con la extensión de archivo .pfx. La ruta de acceso debe ser accesible para todos los demás servidores perimetrales del grupo o disponible para el transporte por medio de medios extraíbles, por ejemplo, una unidad flash USB. Haga clic en **Siguiente**.

13. Revise el resumen en **completar el Asistente para exportación de certificados**y, a continuación, haga clic en **Finalizar**.

14. En el cuadro de diálogo exportación correcta, haga clic en **Aceptar**.

15. Importe el archivo de certificado exportado a los otros servidores perimetrales siguiendo los pasos indicados en el procedimiento "para importar el certificado de la interfaz externa del servidor perimetral" descrito anteriormente en este tema.

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a>Para asignar el certificado para la interfaz externa del servidor perimetral

1.  En cada servidor perimetral, en el Asistente para la implementación, junto al **paso 3: solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.

2.  En la página **tareas de certificados disponibles** , haga clic en **asignar un certificado existente**.

3.  En la página **asignación de certificado** , haga clic en certificado de **borde externo** y seleccione la casilla de verificación **uso avanzado de certificados** .

4.  En la página **uso de certificados avanzado** , active todas las casillas para asignar el certificado para todos los usos.

5.  En la página **almacén de certificados** , seleccione el certificado público que solicitó e importó para la interfaz externa del servidor perimetral.
    
    <div>
    

    > [!NOTE]  
    > Si el certificado solicitado y importado no está en la lista, uno de los métodos de solución de problemas es comprobar que el nombre del sujeto y el asunto de los nombres alternativos del certificado cumplen con todos los requisitos del certificado y, si ha importado manualmente el la cadena de certificados y certificados en lugar de usar los procedimientos anteriores, que el certificado está en el almacén de certificados correcto (el almacén de certificados del equipo, no el almacén de certificados del usuario o servicio).

    
    </div>

6.  En la página **Resumen de asignación de certificado** , revise la configuración y, a continuación, haga clic en **siguiente** para asignar los certificados.

7.  En la página de finalización del asistente, haga clic en **Finalizar**.

8.  Después de usar este procedimiento para asignar el certificado perimetral, abra el complemento certificado en cada servidor, expanda **certificados (equipo local)**, expanda **personal**, haga clic en **certificados**y, después, compruebe en el panel de detalles que el el certificado aparece en la lista.

9.  Si su implementación incluye varios servidores perimetrales, repita este procedimiento para cada servidor perimetral.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

