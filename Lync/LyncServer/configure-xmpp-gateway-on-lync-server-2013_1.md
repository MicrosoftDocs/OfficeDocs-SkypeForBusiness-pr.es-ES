---
title: Configurar la puerta de enlace XMPP en Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49733538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a940209c09f78b75e2a0f75f364841cdb018e2cb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a>Configurar la puerta de enlace XMPP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Cuando se configuran directivas para admitir socios federados del protocolo extensible de mensajería y presencia (XMPP), las directivas se aplican a los usuarios de los dominios federados de XMPP, pero no a los usuarios de los proveedores de servicio de mensajería instantánea (MI) del protocolo de inicio de sesión (SIP) (por ejemplo, Windows Live) o dominios federados de SIP. Se debe configurar un socio federado de XMPP para cada dominio federado de XMPP al que desea permitir que los usuarios agreguen contactos y con el que desea que se comuniquen. Una vez que las directivas se encuentran en su lugar, las tareas adicionales incluyen la configuración de los certificados de puerta de enlace XMPP, la implementación de la puerta de enlace XMPP de Lync Server 2013 y la actualización de los registros DNS para la puerta de enlace XMPP.

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a>Configurar los certificados de la puerta de enlace XMPP en el servidor perimetral de Lync Server 2013

1.  En el servidor perimetral, en el Asistente para la implementación, junto al **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.
    
    <div class=" ">
    

    > [!TIP]  
    > Si es la primera vez que implementa el servidor perimetral, aparecerá Ejecutar en lugar de Ejecutar de nuevo.

    
    </div>

2.  En la página **Tareas de certificado disponibles**, haga clic en **Crear una nueva solicitud de certificado**.

3.  En la página **Solicitud de certificado**, haga clic en **Certificado perimetral externo**.

4.  En la página **Solicitud retrasada o inmediata**, active la casilla **Prepare ahora la solicitud, pero enviarla más tarde**.

5.  En la **Página archivo de solicitud de certificado** , escriba la ruta de acceso completa y el nombre de archivo del archivo en el que se va a guardar la solicitud\\(\_por\_ejemplo, c: CERT externos Edge. cer).

6.  En la página **Especificar plantilla de certificado alternativa**, para usar una plantilla distinta a la plantilla predeterminada WebServer, active la casilla **Usar plantilla de certificado alternativa para la entidad de certificación seleccionada**.

7.  En la página **Nombre y configuración de seguridad**, siga este procedimiento:
    
    1.  En **Nombre descriptivo**, escriba un nombre para mostrar para el certificado.
    
    2.  En **Longitud de bits**, especifique la longitud de bits (normalmente, el valor predeterminado es 2048).
    
    3.  Compruebe que la casilla **Marcar la clave privada del certificado como exportable** esté seleccionada.

8.  En la página **Información de la organización**, escriba un nombre para la organización y la unidad organizativa (por ejemplo, una división o departamento).

9.  En la página **Información geográfica**, escriba la información de ubicación.

10. En la página **Nombre de sujeto/nombres alternativos de sujeto**, la información se rellenará automáticamente gracias al asistente que se muestra. Si necesita otros nombres alternativos de sujeto, especifíquelos en los dos pasos siguientes.

11. En la página **configuración de dominio SIP en nombres alternativos de sujeto (San)** , active la casilla de verificación dominio para agregar un SIP. \<entrada\> sipdomain a la lista de nombres alternativos de sujeto.

12. En la página **Configurar nombres alternativos de sujeto adicionales**, especifique cualquier nombre alternativo del firmante adicional que necesite.
    
    <div class=" ">
    

    > [!TIP]  
    > Si el proxy de XMPP está instalado, las entradas SAN se cumplimentan de forma predeterminada con el nombre de dominio (por ejemplo, contoso.com). Si necesita más entradas, agréguelas en este paso.

    
    </div>

13. En la página **Resumen de la solicitud **, revise la información del certificado que va a usar para generar la solicitud.

14. Cuando finalice la ejecución de los comandos, puede seleccionar la opción **Ver registro** o hacer clic en **Siguiente** para continuar.

15. En la página **Archivo de solicitud de certificado**, podrá ver el archivo de solicitud de firma de certificado (CSR) generado. Para ello, haga clic en Ver o salga del Asistente para certificados haciendo clic en **Finalizar**.

16. Copie el archivo solicitado y envíelo a su autoridad de certificación pública.

17. Después de recibir, importar y asignar el certificado público, debe detener y reiniciar los servicios del servidor perimetral. Para ello, escriba en la consola de administración de Lync Server:
    
       ```console
        Stop-CsWindowsService
       ```
    
       ```console
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a>Configurar una nueva puerta de enlace XMPP de Lync Server 2013

1.  Abra Panel de control de Lync Server

2.  En el barra de navegación izquierda, haga clic en **Federación y acceso externo** y en **Socios federados de XMPP**.

3.  Para crear una configuración, haga clic en **Nuevo**.

4.  Defina la configuración siguiente:

5.  **Dominio principal (**     obligatorio). El dominio principal es el dominio base del socio XMPP. Por ejemplo, escriba **fabrikam.com** en el nombre de dominio del socio XMPP. Esta es una entrada obligatoria.

6.  **Descripción**   la descripción es para notas u otra información de identificación para esta configuración específica. Este campo es opcional.

7.  **Dominios adicionales los**   dominios adicionales son dominios que forman parte del dominio del socio XMPP y que deben incluirse como parte de la comunicación de XMPP permitida. Por ejemplo, si el dominio principal es **fabrikam.com**, se enumerará el resto de los dominios por debajo de fabrikam.com con los que se comunicará por medio de XMPP.

8.  **Tipo de socio**   el **tipo de socio** es un valor obligatorio. Debe elegir uno de los siguientes para describir y aplicar los contactos que pueden agregarse. Puede seleccionar entre:
    
      - **Federado** Un tipo de socio **federado** representa un alto nivel de confianza entre la implementación de Lync Server y el socio XMPP.Este tipo socio es aconsejable para federarse con los servidores de XMPP en la misma empresa o si hay una relación comercial establecida.Los contactos de XMPP en los socios federados pueden:
        
        1.  Agregar los contactos de Lync y ver su presencia sin autorización expresa del usuario de Lync.
        
        2.  Enviar mensajes instantáneos a los contactos de Lync con independencia de que el usuario de Lync los haya agregado a su lista de contactos.
        
        3.  Ver las notas de estado del usuario de Lync.
    
      - **Comprobada** pública un socio **comprobado público** es un proveedor de XMPP público en el que se confía para comprobar la identidad de sus usuarios.Los contactos de XMPP en las redes públicas verificadas pueden agregar contactos de Lync, ver su presencia y enviarles mensajes instantáneos sin autorización expresa de los usuarios de Lync.Los contactos de XMPP de las redes públicas verificadas no pueden ver las notas de estado de los usuarios de Lync.Esta configuración no se recomienda.
    
      - **Público no comprobado** Un socio **público no comprobado** es un proveedor de XMPP público que no tiene la confianza suficiente como para comprobar la identidad de sus usuarios. Los usuarios XMPP de las redes públicas no comprobadas no podrán comunicarse con los usuarios de Lync a menos que el usuario de Lync los haya autorizado expresamente agregándolos a la lista de contactos. Los usuarios XMPP de las redes públicas no comprobadas no pueden ver las notas de estado de los usuarios de Lync. Se recomienda esta configuración para cualquier federación con proveedores XMPP públicos como, por ejemplo, Google Talk.

9.  **Tipo de conexión:** Define las reglas y la configuración de la devolución de llamadas.
    
      - **La negociación**   TLS define las reglas de negociación de TLS. Un servicio de XMPP puede requerir TLS, determinar que TLS es opcional o definir que TLS no se admite. Si se opta por la posibilidad opcional, es el servicio de XMPP quien decide si la negociación es obligatoria. Para ver todos los valores y detalles posibles para la negociación de SASL, TLS y devolución, incluidas las configuraciones de error conocidas y no válidas, vea [configuración de la negociación para socios federados XMPP en Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)
        
           - **Requerido**   el servicio XMPP requiere negociación TLS.
        
           - **Opcional**   el servicio XMPP indica que TLS es de negociación obligatoria.
        
           - **No admitido**   el servicio XMPP no admite TLS.
    
      - **La negociación**   SASL define las reglas de negociación de SASL. Un servicio de XMPP puede requerir SASL, determinar que SASL sea opcional o definir que SASL no se admite. Si se opta por la posibilidad opcional, es el servicio de XMPP de socio quien decide si la negociación es obligatoria.
        
           - **Requerido**   el servicio XMPP requiere negociación SASL.
        
           - **Opcional**   el servicio XMPP indica que SASL es de negociación obligatoria.
        
           - **No admitido**   el servicio XMPP no admite SASL.
    
      - **Servidor de soporte devolución negociación** El proceso de negociación del servidor de soporte devolución usa el sistema de nombres de dominio (DNS) y un servidor autorizado para comprobar que la solicitud procede de un socio de XMPP válido. Para ello, el servidor de origen crea un mensaje de un tipo específico con una clave de rellamada y busca al servidor en el DNS. El servidor de origen envía la clave en un flujo XML al resultado de la búsqueda de DNS, en principio, el servidor destinatario. A recibir la clave por el flujo XML, el servidor destinatario no responde al servidor de origen, sino que envía la clave a un servidor de autorización conocido. Este verifica que la validez de la clave. Si no lo es, el servidor destinatario no responde al servidor de origen. Si lo es, el servidor destinatario informa al servidor de origen de que la identidad y la clave son válidas, y la conversación puede iniciarse.
        
        Existen dos estados válidos en la **negociación de rellamada**:
        
           - **True**   el servidor XMPP está configurado para usar la negociación de devolución si se debe recibir una solicitud de un servidor de origen.
        
           - **False**   el servidor XMPP no está configurado para usar la negociación de devolución y si se debe recibir una solicitud de un servidor de origen, se omitirá.

10. Haga clic en **Confirmar** para guardar los cambios en la directiva de sitio o usuario.

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a>Actualizar los registros de DNS para la puerta de enlace XMPP de Lync server 2013

1.  Para configurar DNS para la Federación XMPP, agregue el siguiente registro SRV a su DNS externo:\_XMPP-Server. \_TCP. \<nombre\> de dominio el registro SRV se resolverá en el FQDN perimetral de acceso del servidor perimetral, con un valor de puerto de 5269.

</div>

</div>

<span> </span>

</div>

</div>

</div>

