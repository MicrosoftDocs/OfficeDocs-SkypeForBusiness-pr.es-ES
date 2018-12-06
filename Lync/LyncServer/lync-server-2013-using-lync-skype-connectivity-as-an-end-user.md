---
title: "Lync Server 2013 : Util. de la connectivité Lync-Skype en tant qu’util. final"
TOCTitle: Usar la conectividad de Lync y Skype como usuario final
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn440175(v=OCS.15)
ms:contentKeyID: 59602844
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Usar la conectividad de Lync y Skype como usuario final en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-27_

La conectividad entre Lync y Skype permite a los usuarios de Skype y a los usuarios de Lync agregarse como contactos, intercambiar mensajes instantáneos y realizar llamadas de audio y vídeo. Cuando un usuario de Skype agrega a un usuario de Lync, el usuario de Skype creará un contacto en Skype con el identificador uniforme de recursos (URI) de protocolo de inicio de sesión (SIP) del usuario de Lync. Al contrario, cuando un usuario de Lync agrega un contacto de Skype, el usuario de Lync creará un contacto en Lync que contendrá la cuenta Microsoft (MSA) del usuario de Skype y no el nombre de usuario de Skype.

**¿Qué es una MSA?** Los usuarios de Skype deben iniciar sesión con una cuenta Microsoft (anteriormente conocida como Windows Live ID) para poder comunicarse con contactos de Lync. Una cuenta Microsoft consiste en la combinación de un correo electrónico y una contraseña que puede usar para iniciar sesión en servicios como la tecnología de almacenamiento Microsoft OneDrive, Windows Phone, el servicio de juego en línea Microsoft Xbox LIVE y el cliente de colaboración y mensajería Microsoft Outlook (y, anteriormente, en el servicio de correo electrónico basado en la Web Microsoft Hotmail o Windows Live Messenger). Si utiliza una dirección de correo electrónico y una contraseña para iniciar sesión en estos u otros servicios, ya tiene una cuenta Microsoft. Para obtener más información sobre la creación de una cuenta Microsoft, consulte la página de registro de cuentas Microsoft en [http://go.microsoft.com/fwlink/p/?LinkId=306061](http://go.microsoft.com/fwlink/p/?linkid=306061). Puede combinar su cuenta de Skype existente con una cuenta Microsoft para poder iniciar sesión una sola vez y utilizar una variedad de aplicaciones y servicios. Una vez que la cuenta esté combinada, el usuario de Skype podrá enviar solicitudes de contacto a los usuarios de Lync.

> [!IMPORTANT]  
> Los usuarios de Lync y de Skype deben cumplir los siguientes requisitos para poder comunicarse entre ellos usando todas las funciones:
> <ul>
> <li><p>Los usuarios de Skype deben tener una sesión iniciada en su cliente de Skype con una MSA.</p></li>
> <li><p>El administrador de Lync debe habilitar la conectividad de mensajería instantánea pública para sus usuarios.</p></li>
> <li><p>Cuando un usuario de Skype agrega un contacto de Lync, compruebe que aparezca la palabra &quot;Lync&quot; debajo del nombre del contacto. Esto indica que se encontró un URI de Lync.</p></li>
> <li><p>Cuando un usuario de Skype agrega un contacto de Lync y no se devuelve ningún resultado de la búsqueda para ese dominio de Lync, puede que no se haya completado el proceso de aprovisionamiento de PIC o que aún no se haya configurado el dominio de Lync.</p></li>
> <li><p>En función de la configuración de privacidad de los usuarios de Lync y Skype, puede que la mensajería instantánea, el vídeo o la presencia no funcionen hasta que los contactos nuevos acepten las solicitudes de contacto.</p></li>
> </ul>


**Para agregar un contacto de Skype a Lync 2013**

1.  En Lync, haga clic en **Agregar un contacto, Agregar un contacto de fuera de mi empresa**.

2.  En la lista de proveedores de contacto disponibles, seleccione **Skype**, como se muestra abajo.
    
    ![Cliente de Lync mostrando cómo agregar un contacto de Skype](images/Dn440175.ac4e2f21-c1d9-47d8-b99e-d49fe4eb36d7(OCS.15).jpg "Cliente de Lync mostrando cómo agregar un contacto de Skype")

3.  En el campo **Dirección de MI**, escriba la MSA del usuario de Skype.

4.  En el cuadro desplegable **Agregar a grupo de contactos**, seleccione el grupo de contactos al que quiera agregar el usuario.

5.  En el cuadro desplegable **Definir relación de privacidad**, seleccione la configuración de contacto correspondiente y haga clic en **Aceptar**.

6.  Ahora el usuario aparecerá como un contacto en Lync. Selecciónelo, haga clic con el botón secundario en el nombre de usuario y haga clic en la opción para **ver la tarjeta de contacto** para ver las propiedades. Tal y como se muestra en la parte inferior, también puede hacer clic en **Llamar** y después en **Llamada de Lync** para establecer una llamada de audio o vídeo con el usuario de Skype recién agregado.
    
    ![Cliente de Lync iniciando una llamada de Lync a un contacto](images/Dn440175.cd7cb21a-87f7-4bfa-b30c-980d4098d226(OCS.15).jpg "Cliente de Lync iniciando una llamada de Lync a un contacto")

Para más información sobre la compatibilidad con contactos, vea los temas acerca de cómo [agregar un contacto en Lync](http://office.microsoft.com/es-es/office365-lync-online-help/add-a-contact-in-lync-ha102828922.aspx) y [agregar un contacto externo en Lync](http://office.microsoft.com/es-es/office365-lync-online-help/add-an-external-contact-in-lync-ha104038998.aspx?ctt=5%26origin=ha102828922)

Cuando la MSA de un usuario de Skype usa un nombre de dominio personalizado, como <strong>bob@contoso.com</strong>, los usuarios de Lync pueden agregarla a Lync de dos formas:

1.  Con el icono **Agregar un contacto**

2.  En el campo **Buscar una persona o una sala, o marcar un número**

En ambos casos, el usuario de Lync debe escribir el correo electrónico del usuario de Skype con el siguiente formato: <strong>usuario(nombre de dominio)@msn.com</strong>.

> [!IMPORTANT]  
> Este paso no es necesario para las MSA que usan los siguientes nombres de dominio: <strong>@live.com, @hotmail.com o @outlook.com</strong>. Para más información sobre los nombres de dominio personalizados admitidos, vea el tema acerca de los <a href="http://support.microsoft.com/kb/897567/es">dominios de mensajería instantánea pública compatibles</a>.



**Para agregar un contacto de Skype a Lync cuando se usa un nombre de dominio personalizado**

1.  En Lync, haga clic en **Agregar un contacto, Agregar un contacto de fuera de mi empresa**.

2.  En la lista de proveedores de contacto disponibles, seleccione **Skype**, como se muestra abajo.
    
    ![Cliente de Lync mostrando cómo agregar un contacto de Skype](images/Dn440175.ac4e2f21-c1d9-47d8-b99e-d49fe4eb36d7(OCS.15).jpg "Cliente de Lync mostrando cómo agregar un contacto de Skype")

3.  En el campo **Dirección de MI,**, escriba la MSA del usuario de Skype con el formato <strong>usuario(nombre de dominio)@msn.com</strong>. Por ejemplo, para el usuario bob@contoso.com, se debería escribir <strong>bob(contoso.com)@msn.com</strong>, como se muestra abajo.
    
    ![Configuración de contactos nuevos del cliente de Lync](images/Dn440175.422e69b5-2c0c-4260-858f-f10309af772f(OCS.15).jpg "Configuración de contactos nuevos del cliente de Lync")

4.  En el cuadro de lista desplegable **Agregar a grupo de contactos**, seleccione el grupo de contactos al que quiera agregar el usuario.

5.  En el cuadro de lista desplegable **Definir relación de privacidad**, seleccione la configuración de contacto correspondiente y haga clic en **Aceptar**.

6.  Los usuarios de Lync también pueden usar el cuadro **Buscar una persona o una sala, o marcar un número** en Lync y agregar una dirección que se parezca a <strong>usuario(nombre de dominio)@msn.com</strong>. Por ejemplo, para la MSA bob@contoso.com, se debería escribir <strong>bob(contoso.com)@msn.com</strong>, como se muestra abajo.
    
    ![Buscar un contacto en un cliente de Lync](images/Dn440175.69787db8-f9b9-49e5-b197-b90b10393301(OCS.15).jpg "Buscar un contacto en un cliente de Lync")

7.  Siga los pasos 4 y 5 anteriores para agregar el contacto a un grupo de contactos y para seleccionar la relación de privacidad correspondiente.

**Para agregar un contacto de Lync a Skype**

1.  Inicie sesión en Skype. El usuario de Skype debe tener una sesión iniciada en su cliente de Skype con una MSA.
    
    ![Página de inicio de sesión en un cliente de Skype](images/Dn440175.b4fd7c5a-be35-4205-80c7-872863b7a91d(OCS.15).jpg "Página de inicio de sesión en un cliente de Skype")

2.  Seleccione el icono Agregar contactos.

3.  Escriba el URI del SIP del usuario de Lync. Por ejemplo, bob@contoso.com.

4.  Cuando Skype encuentre la coincidencia en los resultados de la búsqueda, compruebe si aparece la palabra **Lync** debajo del nombre del usuario de Lync. Esto indica que Skype encontró correctamente el URI del SIP del cliente de Lync. Haga clic en el nombre.
    
    ![Cliente de Skype mostrando un contacto de Lync](images/Dn440175.4e690a72-1a54-4442-89cf-0fb45ac5f56a(OCS.15).jpg "Cliente de Skype mostrando un contacto de Lync")

5.  En la esquina superior derecha de la ventana, haga clic en Agregar contactos.

6.  El nuevo contacto ya se ha agregado a la lista de contactos, pero verá un signo de interrogación en lugar del icono de estado hasta que acepte la solicitud. Cuando el nuevo contacto acepte la solicitud, podrá ver cuándo está conectado, iniciar conversaciones de mensajería instantánea y realizar llamadas de audio y vídeo.
    
    ![Conversación de MI en un cliente de Skype con un contacto de Lync](images/Dn440175.86ca6f81-4db9-45ba-8511-1f7541aaf066(OCS.15).jpg "Conversación de MI en un cliente de Skype con un contacto de Lync")
    
    > [!IMPORTANT]  
    > El administrador de Lync Server debe establecer la configuración de directiva del usuario de Lync para permitir las solicitudes entrantes. Si no lo hace, el usuario no recibirá la solicitud de contacto del usuario de Skype. Según la configuración de directiva del usuario de Lync, la solicitud para agregar el usuario de Skype puede aparecer en la pestaña <strong>Nuevo</strong> del cliente de Lync. Para iniciar una comunicación con el usuario de Skype, debe agregarlo a la lista de Favoritos o a una lista de contactos. La siguiente imagen muestra la ubicación de la pestaña <strong>Nuevo</strong> en el cliente de Lync.
    
    
    ![Página de contactos nuevos del cliente de Lync](images/Dn440175.b1cf8570-1401-47d9-ab14-b04f0d7e8a7a(OCS.15).jpg "Página de contactos nuevos del cliente de Lync")

El usuario de Lync debe configurar las alertas de Lync para asegurarse de que las solicitudes de los usuarios de Skype aparezcan y estén visibles. Para ello, complete este procedimiento.

**Para configurar alertas de Lync**

1.  En el cliente de Lync, haga clic en el icono **Opciones**.

2.  Seleccione **Alertas**.

3.  En **Alertas generales**, active la casilla **Notificarme cuando alguien me agregue a su lista de contactos**.

4.  En **Contactos que no usan Lync**, active la casilla **Permitir invitaciones y bloquear el resto de comunicaciones**.

5.  Haga clic en **Aceptar** para cerrar la ventana Opciones.

![Cuadro de diálogo Opciones de cliente de Lync, página Alertas](images/Dn440175.b36ed67f-f394-4f66-b60a-b74793001bfc(OCS.15).jpg "Cuadro de diálogo Opciones de cliente de Lync, página Alertas")

