---
title: Usar el analizador de conectividad de Lync
TOCTitle: Usar el analizador de conectividad de Lync
ms:assetid: 954953fb-0c7a-4fd5-8acd-68ecb59b20af
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ907302(v=OCS.15)
ms:contentKeyID: 52061719
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Usar el analizador de conectividad de Lync

 

_**Última modificación del tema:** 2016-12-08_

El Lync analizador de conectividad de Microsoft ayuda a los administradores de Lync a determinar si la implementación y la configuración del entorno de Office 365 o del entorno local de Lync Server cumple los requisitos para admitir conexiones desde las aplicaciones Aplicación de la Tienda Windows de Lync y Lync en dispositivos móviles.

El Analizador de conectividad de Lync intenta conectarse al Lync Server local o a Skype Empresarial Online utilizando los mismos servicios y protocolos que utilizan Aplicación de la Tienda Windows de Lync y las aplicaciones móviles de Lync. Puede realizar pruebas de conexión en una red interna o en una red externa que se conecte a Lync Server o Skype Empresarial Online. El Analizador de conectividad de Lync presenta un informe con datos detallados sobre cada paso de la conexión que resulta útil para validar la configuración y solucionar los problemas de conexión que se presenten.

El Analizador de conectividad de Lync prueba los siguientes componentes de Lync Server:

  - Servicio Detección automática

  - Servicio Agente de autenticación (Reach)

  - Servicio Movilidad (MCX)

  - Servicio Movilidad (UCWA)

  - Servicio WebTicket

El Analizador de conectividad de Lync prueba la configuración de estos otros componentes:

  - Publicación de registros DNS para direcciones URL de Detección automática

  - Certificados

  - Servidores proxy

Puede descargar el Analizador de conectividad de Lync desde el Centro de descarga de Microsoft en la dirección <http://go.microsoft.com/fwlink/?linkid=277056>.

## Para analizar la conectividad

1.  Escriba las credenciales de una cuenta de Lync válida (una cuenta de Lync local o una cuenta Lync de Office 365) que usará la herramienta para probar la conexión:
    
      - En **Tipo de cuenta de Lync**, seleccione**Office 365** o **Local**.
    
      - En **URI de SIP**, introduzca la dirección de inicio de sesión de SIP para la conexión de Lync, en formato <strong>usuario@dominio.com</strong>.
    
      - En **Contraseña**, escriba la contraseña asociada a esta cuenta.
    
      - En **Nombre de usuario (opcional)**, escriba un nombre de usuario, en su caso. El nombre de usuario también se conoce como nombre principal de usuario (UPN). Si el nombre de usuario y el URI de SIP son el mismo, no es necesario especificar un nombre de usuario. Si no son el mismo, especifique el nombre de usuario en el formato <strong>usuario@dominio.com</strong> o **dominio\\usuario**, lo que corresponda.
    
      - En **Acceso de red**, elija **Desde dentro de mi organización** si está ejecutando el Analizador de conectividad de Lync desde un equipo conectado a su red interna. De lo contrario, elija **Externo (Internet)**. El Analizador de conectividad de Lync siempre hace pruebas internas y externas, pero si especifica si está dentro o fuera de su propia red, la herramienta podrá interpretar mejor si se esperan determinados fallos.
    
      - En **Cliente**, seleccione si desea realizar pruebas de conectividad para **Lync Windows Store App**, **Lync Mobile 2010 App** o **Lync Mobile 2013 App**.
    
      - En **Detección de servidores**, seleccione el tipo de prueba que se va a llevar a cabo:
        
          - Si quiere que la herramienta detecte el servidor Lync automáticamente, seleccione **Automática**.
        
          - Si quiere que la herramienta omita la prueba de detección automática, o si conoce el nombre del servidor al que desea conectarse, seleccione **Dirección de uso manual:** y especifique el nombre de dominio completo (FQDN) del servidor de Lync, por ejemplo, **lync.company.com**.

2.  (Opcional) En **Archivo de registro**, marque la casilla si desea crear un archivo de registro en la ruta especificada. Si el registro está habilitado, haga clic en **Borrar** para borrar el archivo de registro, en **Abrir** para abrir y ver el archivo de registro, en **Correo electrónico** para abrir un mensaje de correo electrónico para enviar los resultados a su equipo de soporte técnico (tiene que adjuntar el archivo manualmente siguiendo la ruta especificada).

3.  Haga clic en **Iniciar** .

La imagen siguiente muestra resultados de ejemplo del Analizador de conectividad de Lync.

**Analizador de conectividad de Lync**

![Captura de pantalla del analizador de conectividad de Lync](images/JJ907302.a7cc0abe-fac2-4691-a7d8-9ffef59cdee5(OCS.15).png "Captura de pantalla del analizador de conectividad de Lync")

## Componentes probados por el Analizador de conectividad de Lync

El Analizador de conectividad de Lync intenta detectar el servidor Lync y establecer una conexión siguiendo los mismos pasos usados por Aplicación de la Tienda Windows de Lync y aplicaciones móviles de Lync. El Analizador lleva a cabo las pruebas según lo descrito en esta sección.

Si se selecciona **Detección automática**, el Analizador de conectividad de Lync hace lo siguiente:

  - Consulta el Servicio de nombres de dominio (DNS) para detectar automáticamente las URL.

  - Intenta la detección a través del canal interno seguro. Por ejemplo, **HTTPS://lyncdiscoverinternal.company.com/**.

  - Intenta la detección a través del canal interno no seguro. Por ejemplo, **HTTP://lyncdiscoverinternal.company.com/**.

  - Intenta la detección a través del canal externo seguro. Por ejemplo, **HTTPS://lyncdiscover.company.com**.

  - Intentan la detección con el canal externo no seguro. Por ejemplo, **HTTP://lyncdiscover.company.com**.

Si se selecciona **Usar la siguiente dirección de detección del servidor**, el Analizador de conectividad de Lync hace lo siguiente:

  - Consulta el DNS para el FQDN del servidor.

  - Intenta la detección con el canal seguro. Por ejemplo, **HTTPS://serverFQDN/**.

  - Intenta la detección con el canal no seguro. Por ejemplo, **HTTP://serverFQDN/**.

Si se selecciona **Aplicación Tienda de Windows de Lync** en **Probar los requisitos para**, el Analizador de conectividad de Lync hace lo siguiente:

  - Verifica que el servicio WebTicket esté disponible y prueba la autenticación de las credenciales de la cuenta de Lync.

  - Verifica que el servicio Agente de autenticación (Reach) esté disponible.

Si se selecciona **Lync Mobile 2010 App** en **Cliente**, el Analizador de conectividad de Lync hace lo siguiente:

  - Verifica que el servicio WebTicket esté disponible y prueba la autenticación de las credenciales de la cuenta de Lync.

  - Verifica que el servicio Movilidad (MCX) esté disponible.

Si se selecciona **Lync Mobile 2013 App** en **Cliente**, el Analizador de conectividad de Lync hace lo siguiente:

  - Comprueba que el servicio WebTicket esté disponible y prueba la autenticación de las credenciales de la cuenta de Lync.

  - Comprueba que el servicio Movilidad (UCWA) esté disponible.

Mientras lleva a cabo estas pruebas, el Analizador de conectividad de Lync valida los certificados instalados en Lync Server, equilibradores de carga de hardware, servidores proxy y el equipo en el que se están ejecutando las pruebas.

## Otros recursos

Microsoft también proporciona el Analizador de conectividad remota, una herramienta de prueba de conectividad basada en la web y que está disponible en <https://testconnectivity.microsoft.com/>. El Analizador de conectividad de Lync y el Analizador de conectividad remota se diferencian en lo siguiente:

  - El Analizador de conectividad remota puede probar la conectividad de Microsoft Exchange y Outlook, además de Microsoft Lync.

  - El Analizador de conectividad remota completa el inicio de sesión de SIP, mientras que el Analizador de conectividad de Lync solo valida las credenciales de cuenta y no el inicio de sesión.

  - El Analizador de conectividad remota prueba las conexiones únicamente desde fuera de la red de su organización porque se ejecuta desde un servidor web público.

  - El Analizador de conectividad remota no prueba la disponibilidad de los servicios Agente de autenticación (Reach), Movilidad (MCX) y WebTicket.

  - El Analizador de conectividad de Lync prueba el servicio Detección automática.

  - El Analizador de conectividad remota puede conectarse a cualquier versión de Lync Server, mientras que el Analizador de conectividad de Lync solo puede conectarse con éxito a Lync Server 2010 con actualizaciones acumulativas para Lync Server 2010 de febrero de 2012 (como mínimo), o a la versión más reciente de Lync Server.

En la documentación siguiente se describen los requisitos y procedimientos para la implementación y configuración de Lync Server para su compatibilidad con la Aplicación de la Tienda Windows de Lync y los clientes móviles de Lync:

  - [Implementación de clientes y dispositivos en Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)

  - [Planeación de movilidad en Lync Server 2013](lync-server-2013-planning-for-mobility.md)

  - [Implementar la movilidad en Lync Server 2013](lync-server-2013-deploying-mobility.md)

