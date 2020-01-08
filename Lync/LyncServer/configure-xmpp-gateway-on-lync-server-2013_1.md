---
title: Configurar la puerta de enlace XMPP en Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49733538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 185a52322ad0eea681e9a3318787921d9c49453a
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a>Configurar la puerta de enlace XMPP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Al configurar directivas para la compatibilidad de los socios federados protocolo de presencia y mensajería extensible (XMPP), las directivas se aplican a los usuarios de XMPP Federated Domains, pero no a los usuarios de proveedores de servicios de mensajería instantánea (mi) protocolo de inicio de sesión (SIP) (por ejemplo, Windows Live) o dominios federados de SIP. Configure un socio de XMPP federado para cada dominio de XMPP federado que desee permitir a los usuarios que añadan contactos y se comuniquen con ellos. Una vez que las directivas están instaladas, las tareas adicionales incluyen la configuración de los certificados de la puerta de enlace XMPP, la implementación de la puerta de enlace XMPP de Lync Server 2013 y, por último, la actualización de los registros DNS para la puerta de enlace XMPP.

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a>Configurar certificados de puerta de enlace XMPP en el servidor perimetral 2013 de Lync Server

1.  En el servidor perimetral, en el Asistente para la implementación, junto al **paso 3: solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.
    
    <div class=" ">
    

    > [!TIP]  
    > Si está implementando el servidor perimetral por primera vez, verá ejecutar en lugar de volver a ejecutar.

    
    </div>

2.  En la página **Tareas de certificado disponibles**, haga clic en **Crear una nueva solicitud de certificado**.

3.  En la página **solicitud de certificado** , haga clic en certificado de **borde externo**.

4.  En la página **solicitud inmediata o demorada** , active la casilla **preparar la solicitud ahora pero enviarla más tarde** .

5.  En la **Página archivo de solicitud de certificado** , escriba la ruta de acceso completa y el nombre del archivo en el que se va a guardar la solicitud (por\\ejemplo\_,\_c: CERT la Edge. cer).

6.  En la página **especificar plantilla de certificado alternativa** , para usar una plantilla distinta de la plantilla predeterminada de WebServer, seleccione la casilla **Usar plantilla de certificado alternativa para la entidad emisora de certificados seleccionada** .

7.  En la página **nombre y configuración de seguridad** , haga lo siguiente:
    
    1.  En **nombre descriptivo**, escriba un nombre para mostrar para el certificado.
    
    2.  En **longitud bit**, especifique la longitud en bits (normalmente, el valor predeterminado de 2048).
    
    3.  Compruebe que la casilla **marcar clave privada de certificado como exportable** está activada.

8.  En la página información de la **organización** , escriba el nombre de la organización y la unidad organizativa (por ejemplo, una división o un departamento).

9.  En la página **información geográfica** , especifique la información de ubicación.

10. En la página **nombre de sujeto/nombres alternativos de asunto** , se muestra la información que el asistente rellenará automáticamente. Si se necesitan nombres alternativos adicionales, debe especificarlos en los dos pasos siguientes.

11. En la página **configuración del dominio SIP en la página de nombres alternativos de asunto (San)** , seleccione la casilla dominio para agregar un SIP. \<sipdomain\> entrada a la lista de nombres alternativos de asunto.

12. En la página **configurar otros nombres alternativos de asunto** , especifique los nombres alternativos adicionales que sean obligatorios.
    
    <div class=" ">
    

    > [!TIP]  
    > Si el proxy XMPP está instalado, de forma predeterminada, el nombre de dominio (por ejemplo, contoso.com) se rellena en las entradas SAN. Si necesita más entradas, agréguelos en este paso.

    
    </div>

13. En la página **solicitar Resumen** , revise la información del certificado que se va a usar para generar la solicitud.

14. Cuando termine de ejecutarse los comandos, puede **ver el registro**o hacer clic en **siguiente** para continuar.

15. En la página de **archivo de solicitud de certificado** , puede ver el archivo de solicitud de firma de certificado generado (CSR) haciendo clic en ver o salir del asistente de certificados haciendo clic en **Finalizar**.

16. Copie el archivo de solicitud y envíelo a la entidad emisora de certificados pública.

17. Después de recibir, importar y asignar el certificado público, debe detener y reiniciar los servicios del servidor perimetral. Esto se hace escribiendo en la consola de administración de Lync Server:
    
       ```console
        Stop-CsWindowsService
       ```
    
       ```console
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a>Configurar una nueva puerta de enlace de Lync Server 2013 XMPP

1.  Abra el Panel de control de Lync Server.

2.  En la barra de navegación izquierda, haga clic en **Federación y acceso externo** y, a continuación, haga clic en **XMPP federados**.

3.  Para crear una configuración nueva, haga clic en **nuevo**.

4.  Defina la configuración siguiente:

5.  **Dominio principal (**     obligatorio). El dominio principal es el dominio base del socio XMPP. Por ejemplo, tendría que escribir **fabrikam.com** para el nombre de dominio del socio XMPP. Esta es una entrada obligatoria.

6.  **Descripción**   la descripción es para notas u otras informaciones identificativas para esta configuración en particular. Esta entrada es opcional.

7.  **Dominios adicionales los**   dominios adicionales son dominios que forman parte del dominio del asociado XMPP y que deben incluirse como parte de la comunicación XMPP permitida. Por ejemplo, si el dominio principal es **fabrikam.com**, se mostrarán todos los demás dominios de fabrikam.com con los que se comunicará mediante XMPP.

8.  **Tipo de socio**   el **tipo de socio** es un valor obligatorio. Debe elegir una de las siguientes opciones para describir y exigir qué contactos se pueden agregar. Puede seleccionar:
    
      - **Federado** Un tipo de socio **federado** representa un alto nivel de confianza entre la implementación de Lync Server y el socio XMPP.Este tipo de socio es recomendable para la Federación con servidores XMPP dentro de la misma empresa o cuando existe una relación comercial establecida.Los contactos XMPP de los socios federados pueden:
        
        1.  Agregar contactos de Lync y ver su presencia sin autorización expresa por parte del usuario de Lync.
        
        2.  Enviar mensajes instantáneos a los contactos de Lync si el usuario de Lync los ha agregado a su lista de contactos.
        
        3.  Vea las notas de estado de un usuario de Lync.
    
      - **Pública verificada** un socio **verificado públicamente** es un proveedor de XMPP público en el que se confía para comprobar la identidad de los usuarios.Los contactos XMPP pueden agregar contactos de Lync y ver su estado de presencia y enviarles mensajes instantáneos sin autorización expresa de los usuarios de Lync.Los contactos XMPP de las redes públicas verificadas nunca ven las notas de estado de los usuarios de Lync.No se recomienda esta opción.
    
      - No se ha **comprobado el público** Un socio **público no verificado** es un proveedor de XMPP público en el que no se confía para comprobar la identidad de los usuarios.Los usuarios XMPP de redes públicas no verificadas no pueden comunicarse con los usuarios de Lync a menos que el usuario de Lync los haya autorizado expresamente agregándolos a la lista de contactos.Los usuarios XMPP de redes públicas sin verificar nunca ven las notas de estado de los usuarios de Lync.Se recomienda esta opción para cualquier federación con proveedores de XMPP público, como Google Talk.

9.  **Tipo de conexión:** Define las diversas reglas y la configuración de Dialback.
    
      - **La negociación**   TLS define las reglas de negociación de TLS. Un servicio XMPP puede requerir TLS, puede hacer que TLS sea opcional o usted define que no se admite la TLS. Si elige opcional, el requisito quedará en el servicio XMPP para una decisión obligatoria para la negociación. Para ver todas las configuraciones posibles y los detalles de la negociación SASL, TLS y Dialback, incluidas las configuraciones no válidas y de errores conocidos, vea [configuración de la negociación para socios de XMPP federados en Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)
        
           - **Requerido**   el servicio XMPP requiere la negociación de TLS.
        
           - **Opcional**   el servicio XMPP indica que TLS es obligatorio para negociar.
        
           - **No admitido**   el servicio XMPP no admite TLS.
    
      - **La negociación**   SASL define las reglas de negociación de SASL. Un servicio XMPP puede requerir SASL, puede hacer que SASL sea opcional o usted define que SASL no es compatible. Si elige opcional, el servicio XMPP del socio dejará de ser necesario para una decisión obligatoria para la negociación.
        
           - **Requerido**   el servicio XMPP requiere negociación SASL.
        
           - **Opcional**   el servicio XMPP indica que SASL es obligatorio para negociar.
        
           - **No admitido**   el servicio XMPP no admite SASL.
    
      - **Soporte de servidor de soporte Dialback negociación** El proceso de negociación del servidor de soporte Dialback usa el sistema de nombres de dominio (DNS) y un servidor autorizado para comprobar que la solicitud procede de un socio XMPP válido. Para ello, el servidor de origen crea un mensaje de un tipo específico con una clave de Dialback generada y busca el servidor de recepción en DNS. El servidor de origen envía la clave en una secuencia XML a la búsqueda DNS resultante, supuestamente el servidor de recepción. Al recibir la clave sobre la secuencia XML, el servidor de recepción no responde al servidor de origen, pero envía la clave a un servidor conocido de autorización. El servidor autorizado verifica que la clave sea válida o no válida. Si no es válido, el servidor de recepción no responde al servidor de origen. Si la clave es válida, el servidor receptor informa al servidor de origen de que la identidad y la clave son válidas y que la conversación puede comenzar.
        
        Existen dos Estados válidos para la **negociación de Dialback**:
        
           - **True**   : el servidor XMPP está configurado para usar la negociación de Dialback si se debe recibir una solicitud de un servidor de origen.
        
           - **False**   el servidor XMPP no está configurado para usar la negociación de Dialback y, si se debe recibir una solicitud de un servidor de origen, se pasará por alto.

10. Haga clic en **confirmar** para guardar los cambios en el sitio o en la Directiva de usuario.

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a>Actualizar registros DNS para Lync Server 2013 puerta de enlace XMPP

1.  Para configurar DNS para la Federación XMPP, agregue el siguiente registro SRV a su DNS externo:\_XMPP-Server. \_TCP. \<nombre\> de dominio el registro SRV se resolverá en el FQDN perimetral de acceso del servidor perimetral, con un valor de puerto de 5269.

</div>

</div>

<span> </span>

</div>

</div>

</div>

