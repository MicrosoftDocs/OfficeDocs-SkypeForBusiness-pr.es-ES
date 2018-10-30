---
title: Configurar la puerta de enlace XMPP en Lync Server 2013
TOCTitle: Configurar la puerta de enlace XMPP en Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49888769
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la puerta de enlace XMPP en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-19_

Cuando configure directivas para admitir socios federados que usen el protocolo extensible de mensajería y presencia (XMPP), dichas directivas se aplican a los usuarios de los dominios federados XMPP y no a los usuarios de proveedores de servicios de mensajería instantánea (MI) que usen el protocolo de inicio de sesión (SIP) (como, por ejemplo, Windows Live) ni a los dominios SIP federados. Puede configurar un socio federado XMPP para cada dominio federado XMPP con el que desee que los usuarios agreguen contactos y se comuniquen. Una vez configuradas las directivas, es necesario llevar a cabo tareas adicionales como, por ejemplo, la configuración de los certificados de puerta de enlace XMPP, la implementación de la puerta de enlace XMPP de Lync Server 2013 y, por último, la actualización de los registros DNS para la puerta de enlace XMPP.

## Configurar los certificados de la puerta de enlace XMPP en el servidor perimetral de Lync Server 2013

1.  En el Asistente para la implementación del servidor perimetral, junto a **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.
    
    > [!TIP]  
    > Si es la primera vez que implementa el servidor perimetral, aparecerá Ejecutar en lugar de Ejecutar de nuevo.
    


2.  En la página **Tareas de certificado disponibles**, haga clic en **Crear una nueva solicitud de certificado**.

3.  En la página **Solicitud de certificado**, haga clic en **Certificado perimetral externo**.

4.  En la página **Solicitud retrasada o inmediata**, active la casilla **Prepare ahora la solicitud, pero enviarla más tarde**.

5.  En la página **Archivo de solicitud de certificados**, escriba la ruta de acceso completa y el nombre del archivo en el que se guardará la solicitud (por ejemplo, c:\\cert\_exernal\_edge.cer).

6.  En la página **Especificar plantilla de certificado alternativa**, para usar una plantilla distinta a la plantilla predeterminada WebServer, active la casilla **Usar plantilla de certificado alternativa para la entidad de certificación seleccionada**.

7.  En la página **Nombre y configuración de seguridad**, siga este procedimiento:
    
    1.  En **Nombre descriptivo**, escriba un nombre para mostrar para el certificado.
    
    2.  En **Longitud de bits**, especifique la longitud de bits (normalmente, el valor predeterminado es 2048).
    
    3.  Compruebe que la casilla **Marcar la clave privada del certificado como exportable** está activada.

8.  En la página **Información de la organización**, escriba un nombre para la organización y la unidad organizativa (por ejemplo, una división o departamento).

9.  En la página **Información geográfica**, escriba la información de ubicación.

10. En la página **Nombre de sujeto/nombres alternativos de sujeto**, la información se rellenará automáticamente gracias al asistente que se muestra. Si necesita otros nombres alternativos del firmante, especifíquelos en los dos pasos siguientes.

11. En la página **Configuración de dominio SIP en nombres alternativos de sujeto (SAN)**, active la casilla del dominio para agregar una entrada sip.\<dominiosip\> a la lista de nombres alternativos del firmante.

12. En la página **Configurar nombres alternativos de sujeto adicionales**, especifique cualquier nombre alternativo del firmante adicional que necesite.
    
    > [!TIP]  
    > Si el proxy de XMPP está instalado, las entradas SAN se cumplimentan de forma predeterminada con el nombre de dominio (por ejemplo, contoso.com). Si necesita más entradas, agréguelas en este paso.
    


13. En la página **Resumen de la solicitud**, revise la información del certificado que va a usar para generar la solicitud.

14. Cuando finalice la ejecución de los comandos, puede seleccionar la opción **Ver registro** o hacer clic en **Siguiente** para continuar.

15. En la página **Archivo de solicitud de certificado**, podrá ver el archivo de solicitud de firma de certificado (CSR) generado. Para ello, haga clic en Ver o salga del Asistente para certificados haciendo clic en **Finalizar**.

16. Copie el archivo de solicitud y envíelo a la entidad de certificación pública.

17. Después de recibir, importar y asignar el certificado público, debe detener y reiniciar los servicios del servidor perimetral. Para ello, escriba en la consola de administración de Lync Server:
    
    ```
    Stop-CsWindowsService
    ```
    ```
    Start-CsWindowsService
    ```

## Configurar una nueva puerta de enlace XMPP de Lync Server 2013

1.  Abra Panel de control de Lync Server.

2.  En el barra de navegación izquierda, haga clic en **Federación y acceso externo** y en **Socios federados de XMPP**.

3.  Para crear una configuración, haga clic en **Nuevo**.

4.  Defina la configuración siguiente:

5.  **Dominio principal**    Obligatorio. El dominio principal es el dominio base del socio de XMPP. Por ejemplo, escriba **fabrikam.com** para el nombre de dominio de socio de XMPP. Es un campo obligatorio.

6.  **Descripción**   La descripción es para las notas u otra información de identificación de esta configuración determinada. Este campo es opcional.

7.  **Dominios adicionales**   Son dominios que forman parte del dominio del socio de XMPP que debe incluirse como parte de la comunicación de XMPP permitida. Por ejemplo, si el dominio principal es **fabrikam.com**, se enumerará el resto de los dominios por debajo de fabrikam.com con los que se comunicará por medio de XMPP.

8.  **Tipo de socio**   El **tipo de socio** es un valor obligatorio. Debe elegir uno de los siguientes para describir y aplicar los contactos que pueden agregarse. Puede seleccionar entre:
    
      - **Federado**   Un tipo de socio **federado** representa un alto nivel de confianza entre la implementación de Lync Server y el socio de XMPP. Este tipo socio es aconsejable para federarse con los servidores de XMPP en la misma empresa o si hay una relación comercial establecida. Los contactos de XMPP en los socios federados pueden:
        
        1.  Agregar los contactos de Lync y ver su presencia sin autorización expresa del usuario de Lync.
        
        2.  Enviar mensajes instantáneos a los contactos de Lync con independencia de que el usuario de Lync los haya agregado a su lista de contactos.
        
        3.  Ver las notas de estado del usuario de Lync.
    
      - **Público verificado**   Un socio **público verificado** es un proveedor de XMPP público a quien se le otorga la confianza para verificar la identidad de sus usuarios. Los contactos de XMPP en las redes públicas verificadas pueden agregar contactos de Lync, ver su presencia y enviarles mensajes instantáneos sin autorización expresa de los usuarios de Lync. Los contactos de XMPP de las redes públicas verificadas no pueden ver las notas de estado de los usuarios de Lync. Este valor no se recomienda.
    
      - **Público no verificado**   Un socio **público no verificado** es un proveedor de XMPP público a quien no se le otorga la confianza para verificar la identidad de sus usuarios. Los usuarios de XMPP de las redes públicas no verificadas solo pueden comunicarse con los usuarios de Lync si estos lo han autorizado expresamente y los han agregado a su lista de contactos. Los usuarios de XMPP de las redes públicas no verificadas no pueden ver las notas de estado de los usuarios de Lync. Este valor no se recomienda para las federaciones con proveedores de XMPP públicos, como Google Talk.

9.  **Tipo de conexión:** define las diversas reglas y valores de rellamada.
    
      - **Negociación TLS**   Define las reglas de negociación TLS. Un servicio XMPP puede requerir TLS, requerir TLS de manera opcional o puede establecer que TLS no es compatible. Si se selecciona la opción Opcional, será el servicio XMPP el que tendrá que tomar una decisión de negociación obligatoria. Para ver todas las configuraciones posibles y los detalles de la negociación de devolución de llamada, TLS y SASL (incluidas las configuraciones no válidas y erróneas), vea [Configuración de la negociación para socios federados XMPP en Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)
        
          -   
            **Obligatorio**   El servicio de XMPP requiere la negociación TLS.
        
          -   
            **Opcional**   El servicio de XMPP determina que TLS es de negociación obligatoria.
        
          -   
            **No admitido**   El servicio de XMPP no admite TLS.
    
      - **Negociación SASL**   Define las reglas de negociación de SASL. Un servicio de XMPP puede requerir SASL, determinar que SASL sea opcional o definir que SASL no se admite. Si se opta por la posibilidad opcional, es el servicio de XMPP de socio quien decide si la negociación es obligatoria.
        
          -   
            **Obligatorio**  El servicio de XMPP requiere la negociación SASL.
        
          -   
            **Opcional**   El servicio de XMPP determina que SASL es de negociación obligatoria.
        
          -   
            **No admitido**   El servicio de XMPP no admite SASL.
    
      - **Negociación de rellamada de servidor compatible** El proceso de negociación de rellamada de servidor compatible usa el sistema de nombres de dominio (DNS) y un servidor de autorización para verificar que la solicitud procede de un socio de XMPP válido. Para ello, el servidor de origen crea un mensaje de un tipo específico con una clave de rellamada y busca al servidor en el DNS. El servidor de origen envía la clave en un flujo XML al resultado de la búsqueda de DNS, en principio, el servidor destinatario. A recibir la clave por el flujo XML, el servidor destinatario no responde al servidor de origen, sino que envía la clave a un servidor de autorización conocido. Este verifica que la validez de la clave. Si no lo es, el servidor destinatario no responde al servidor de origen. Si lo es, el servidor destinatario informa al servidor de origen de que la identidad y la clave son válidas, y la conversación puede iniciarse.
        
        Existen dos estados válidos en la **negociación de rellamada**:
        
          -   
            **True**   El servidor de XMPP está configurado para usar la negociación de rellamada en el caso de que se reciba una solicitud de un servidor de origen.
        
          -   
            **False**   El servidor de XMPP no está configurado para usar la negociación de rellamada y se pasarán por alto las solicitudes que se reciban de un servidor de origen.

10. Haga clic en **Confirmar** para guardar los cambios en la directiva de sitio o usuario.

## Actualizar los registros de DNS para la puerta de enlace XMPP de Lync server 2013

1.  Para configurar el DNS para la federación de XMPP, debe agregar el siguiente registro SRV al DNS externo:\_xmpp-server.\_tcp.\<nombre de dominio\>. El registro SRV resolverá el FQDN del servidor perimetral de acceso del servidor perimetral, con el valor de puerto 5269.

