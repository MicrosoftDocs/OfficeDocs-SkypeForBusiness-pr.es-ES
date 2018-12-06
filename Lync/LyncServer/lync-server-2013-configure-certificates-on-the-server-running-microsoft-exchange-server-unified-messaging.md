---
title: "Configurar certificados en servidor con mensajería unificada de MS Exchange Server"
TOCTitle: "Conf. certif. sur le serv. exécutant la mess. un. Microsoft Exchange Server"
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48275703
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar certificados en el servidor que ejecuta la mensajería unificada de Microsoft Exchange Server

 

_**Última modificación del tema:** 2016-12-08_

Si ha implementado la Mensajería unificada de Exchange (UM), como se describe en [Planear la integración de la mensajería unificada de Exchange en Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md), en la documentación referente a la planeación, y desea proporcionar las características de la Mensajería unificada de Exchange a los usuarios de Telefonía IP empresarial de su organización, puede usar los siguientes procedimientos para configurar el certificado en el servidor que ejecuta la Mensajería unificada de Exchange.

> [!IMPORTANT]  
> Para los certificados internos, los servidores que ejecutan Lync Server 2013 y los servidores que ejecutan Microsoft Exchange deben tener certificados de entidad de certificación raíz de confianza que sean de confianza mutua. La entidad de certificación (CA) puede ser la misma o una entidad diferente siempre que los servidores tengan el certificado raíz de entidad de certificación registrado en su almacén de certificados de entidad de certificación raíz de confianza.



El servidor Exchange debe configurarse con un certificado de servidor para poder conectarse a Lync Server 2013:

1.  Descargue el certificado de la entidad de certificación del servidor Exchange.

2.  Instale el certificado de la entidad de certificación del servidor Exchange.

3.  Compruebe que la entidad de certificación figura en la lista de entidades de certificación raíz de confianza del servidor Exchange.

4.  Cree una solicitud de certificado para el servidor Exchange e instale el certificado.

5.  Asigne el certificado para el servidor Exchange.

## Para descargar el certificado de la entidad de certificación

1.  En el servidor que ejecuta Mensajería unificada de Exchange, haga clic en **Inicio** y en **Ejecutar**, escriba **http://\<nombre del servidor de la entidad de certificación emisora\>/certsrv** y, a continuación, haga clic en **Aceptar**.

2.  En **Seleccione una tarea**, haga clic en **Descargar un CRL, cadena de certificados o certificado de la entidad de certificación**.

3.  En **Descargar certificado de CA, cadena de certificados o CRL**, seleccione **Método de codificación en Base 64** y haga clic en **Descargar certificado de CA**.
    

    > [!NOTE]
    > También puede especificar las reglas de codificación distinguida (DER) en este paso. Si selecciona la codificación DER, en el paso siguiente de este procedimiento y en el paso 10 de <STRONG>Para instalar el certificado de la entidad de certificación</STRONG>, el tipo de archivo es .p7b, en lugar de .cer.



4.  En el cuadro de diálogo **Descarga de archivo**, haga clic en **Guardar** y guarde el archivo en disco duro del servidor. (El archivo tendrá una extensión de archivo .cer o .p7b, según la codificación que haya seleccionado en el paso anterior).

## Para instalar el certificado de la entidad de certificación

1.  En el servidor que ejecuta Mensajería unificada de Exchange, abra Microsoft Management Console (MMC). Para ello, haga clic en **Inicio** y en **Ejecutar**, escriba **mmc** en el cuadro **Abrir** y, a continuación, haga clic en **Aceptar**.

2.  En el menú **Archivo**, haga clic en **Agregar o quitar complemento** y, a continuación, en **Agregar**.

3.  En el cuadro **Agregar complementos independientes**, haga clic en **Certificados** y, a continuación, en **Agregar**.

4.  En el cuadro de diálogo **Complemento de certificados**, haga clic en **Cuenta de equipo** y, a continuación, haga clic en **Siguiente**.

5.  En el cuadro de diálogo **Seleccionar equipo**, compruebe que la casilla **Equipo local: (el equipo en el que se está ejecutando esta consola)** esté activada y, después, haga clic en **Finalizar**.

6.  Haga clic en **Cerrar** y, a continuación, en **Aceptar**.

7.  En el árbol de la consola, expanda **Certificados (equipo local)**, expanda **Entidades de certificación raíz de confianza** y, a continuación, haga clic en **Certificados**.

8.  Haga clic con el botón secundario en **Certificados**, haga clic en **Todas las tareas** y, a continuación, haga clic en **Importar**.

9.  Haga clic en **Siguiente**.

10. Haga clic en **Examinar** para buscar el archivo y, a continuación, haga clic en **Siguiente**. (El archivo tendrá una extensión de archivo .cer o .p7b, según la codificación que haya seleccionado en el paso 3 de **Para descargar un certificado de la entidad de certificación**).

11. Haga clic en **Colocar todos los certificados en el siguiente almacén**.

12. Haga clic en **Examinar** y seleccione **Entidades de certificación raíz de confianza**.

13. Haga clic en **Siguiente** para comprobar la configuración y, a continuación, haga clic en **Finalizar**.

## Para comprobar que la entidad de certificación figura en la lista de entidades de certificación raíz de confianza

1.  En el servidor que ejecuta Mensajería unificada de Exchange, en MMC, expanda **Certificados (equipo local)**, expanda **Entidades de certificación raíz de confianza** y, a continuación, haga clic en **Certificados**.

2.  En el panel de detalles, compruebe que su entidad de certificación figura en la lista de entidades de certificación de confianza.

## Para configurar la Mensajería unificada de Exchange Server 2013 con Lync Server

1.  Para más información, consulte la información referente a Microsoft Lync Server 2013 Preview en la documentación sobre Lync Server disponible en [http://go.microsoft.com/fwlink/?linkid=265372\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=265372%26clcid=0xc0a).

## Para crear una solicitud de certificado e instalar el certificado en Exchange Server 2007 (SP1)

1.  En el servidor que ejecuta Mensajería unificada de Exchange, haga clic en **Inicio** y en **Ejecutar**, escriba **http://\<***nombre del servidor de la entidad de certificación emisora***\>/certsrv** y, a continuación, haga clic en **Aceptar**.

2.  En **Seleccione una tarea**, haga clic en **Solicitar un certificado**.

3.  En **Solicitar un certificado**, haga clic en **Solicitud de certificado avanzada**.

4.  En **Solicitud de certificado avanzada**, haga clic en **Crear y enviar una solicitud a esta entidad de certificación**.

5.  En **Solicitud de certificado avanzada**, seleccione **Servidor web** u otra plantilla de certificados de servidor configurada para autenticación de servidor.

6.  En **Identificación de información para plantillas sin conexión**, en el cuadro **Nombre**, escriba el nombre de dominio completo (FQDN) del servidor Exchange.
    

    > [!NOTE]
    > Debe escribir el FQDN del servidor Exchange para que las comunicaciones funcionen.



7.  En **Opciones de clave**, active la casilla **Almacenar el certificado en el almacén de certificados del equipo local**.

8.  Haga clic en el botón **Enviar** en la parte inferior de la página web.

9.  En el cuadro de diálogo que se abre para pedir confirmación, haga clic en **Sí**.

10. En la página Certificado emitido, en **Certificado emitido**, haga clic en **Instalar este certificado**.

11. En el cuadro de diálogo que se abre para pedir confirmación, haga clic en **Sí**.

12. Compruebe que aparece el mensaje "Su nuevo certificado se ha instalado correctamente".

## Para crear un certificado en Exchange Server 2010

1.  Inicie sesión en el servidor que ejecuta Mensajería unificada de Exchange con los derechos de usuario que correspondan. Para obtener más información, consulte "Permisos de acceso de cliente" en [http://go.microsoft.com/fwlink/?linkid=195499\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=195499%26clcid=0xc0a).

2.  Consulte los siguientes procedimientos para crear el certificado:
    
    1.  "Crear un nuevo certificado de Exchange" en [http://go.microsoft.com/fwlink/?linkid=195494\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=195494%26clcid=0xc0a)
    
    2.  "Importar un certificado de Exchange" en [http://go.microsoft.com/fwlink/?linkid=195496\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=195496%26clcid=0xc0a)
    

    > [!NOTE]
    > Para el certificado <STRONG>Nombre de sujeto</STRONG>, debe escribir el FQDN del servidor Exchange para que las comunicaciones funcionen.



## Para asignar el certificado en Exchange Server 2007 (SP1)

1.  En el servidor que ejecuta Mensajería unificada de Exchange, abra MMC.

2.  En el árbol de la consola, expanda **Personal** y, a continuación, haga clic en **Certificados**.

3.  En el panel de detalles, compruebe que se muestra el certificado personal.

4.  Haga doble clic en el certificado para leer sus detalles y asegurarse de que es válido.
    

    > [!NOTE]
    > El certificado puede tardar algunos minutos en mostrarse como válido.



5.  Reinicie el servicio de Mensajería unificada de Microsoft Exchange.
    

    > [!NOTE]
    > El servidor que ejecuta Mensajería unificada de Exchange Server 2007 SP1 recupera automáticamente el certificado correcto.



6.  Abra el Visor de eventos y busque el identificador de evento 1112, que especifica qué certificado ha recuperado el servidor que ejecuta Mensajería unificada de Exchange Server 2007 SP1.

## Para asignar el certificado en Exchange Server 2010

1.  Inicie sesión en el servidor que ejecuta Mensajería unificada de Exchange con los derechos de usuario que correspondan. Para obtener más información, consulte "Permisos de acceso de cliente" en [http://go.microsoft.com/fwlink/?linkid=195499\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=195499%26clcid=0xc0a).

2.  Para ver el procedimiento de asignación del certificado, consulte "Asignar servicios a un certificado" en [http://go.microsoft.com/fwlink/?linkid=195497\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=195497%26clcid=0xc0a).

