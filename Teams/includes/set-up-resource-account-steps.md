En Microsoft Teams, se requiere una cuenta de recursos para cada operador automático o cola de llamadas. También se pueden asignar números de teléfono de servicio a las cuentas de recursos. Así se asignan números de teléfono a operadores automáticos y colas de llamadas, lo que permite que los autores de llamadas de fuera de Teams lleguen al operador automático o a la cola de llamadas.

Este artículo trata sobre cómo crear cuentas de recursos y prepararlas para su uso con operadores automáticos y colas de llamadas.

Antes de empezar los procedimientos de este artículo, asegúrese de que ha hecho lo siguiente:

- [Obtener licencias de usuario virtual](#obtain-virtual-user-licenses)
- [Obtener números de servicio](#obtain-service-numbers)

> [!NOTE]
> Las cuentas de recursos usadas para operadores automáticos y colas de llamadas están deshabilitadas para iniciar sesión y deben permanecer así. El chat y la presencia no están disponibles para estas cuentas.

### <a name="obtain-virtual-user-licenses"></a>Obtener licencias de usuario virtual

Cada cuenta de recursos requiere una licencia para trabajar con operadores automáticos y colas de llamadas. Puedes usar una licencia gratuita *Teléfono Microsoft Teams Standard - Virtual User*. Para obtener estas licencias, consulte [Licencia de usuario virtual](../teams-add-on-licensing/virtual-user.md).

Explicamos cómo [asignar la licencia a una cuenta de recursos más adelante en este artículo](#assign-a-license).

Si compró **Teléfono Teams Estándar** o **Teams Teléfono con** licencias de paquete de Plan de llamadas, las licencias virtuales ya están en su cuenta.

Para ver si ya tiene licencias virtuales, inicie sesión en Microsoft 365 con una cuenta con permisos de administrador global. A continuación, ve a [Facturación > Tus productos](https://admin.microsoft.com/Adminportal/Home#/subscriptions). Si tienes licencias virtuales, aparecerán como **Teléfono Microsoft Teams Estándar - Usuario virtual**.

1. Abra la Centro de administración de Microsoft 365 e inicie sesión con un usuario que sea administrador global. Esta suele ser la cuenta que usaste para registrarte en Microsoft 365.
2. En el panel de navegación izquierdo, ve a **Complementos** >  de servicios  >  de [**compra** **de facturación** > ](https://admin.microsoft.com/Adminportal/Home#/catalog)**Ver todos los productos de complementos**.
3. Desplázate hasta el final para buscar la **licencia Teléfono Microsoft Teams Standard – Virtual User**. Selecciona **Detalles** y, a continuación, **Comprar**.
4. En la página de compra de licencias, seleccione el número de licencias de usuario virtual que desee. Necesita una licencia virtual para cada operador automático y cola de llamadas que planee configurar. Se recomienda seleccionar al menos cinco licencias para que pueda configurar fácilmente más operadores automáticos y colas de llamadas en el futuro sin tener que comprar más licencias inmediatamente.
5. Desactive **Asignar automáticamente a todos los usuarios sin licencias**.
6. Selecciona **Echar un vistazo ahora**.
7. Confirma el pedido, selecciona **Siguiente** y, a continuación, **Realizar pedido**.

Hay un costo cero, pero aún debe seguir estos pasos para adquirir la licencia.

### <a name="obtain-service-numbers"></a>Obtener números de servicio

Los números de servicio son opcionales para los operadores automáticos y las colas de llamadas, pero necesitará al menos un número de servicio para que los autores de llamadas lleguen a su operador automático y la configuración de la cola de llamadas. Para cualquier operador automático o cola de llamadas al que desee que un número de servicio le pueda contactar directamente, debe tener una cuenta de recurso con un número de servicio asociado.

Las cuentas de recursos pueden usar números de servicio de pago o gratuitos. Puede solicitar números nuevos o transferir números existentes de otro operador.

Para obtener nuevos números de servicio, consulte [Obtener números de teléfono de servicio](../getting-service-phone-numbers.md).

Para realizar la portabilidad de un número de otro operador, vea [Transferir números de teléfono a Teams](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

## <a name="create-a-resource-account"></a>Crear una cuenta de recursos

Puede crear una cuenta de recursos en el centro de administración de Teams.

1. En el Teams centro de administración, expanda **Voz** y, después, seleccione **Cuentas de recursos**.
2. Seleccione **Agregar**.
3. En el panel **Agregar cuenta de recurso** , rellene **Nombre para mostrar**, **Nombre de usuario** y el **tipo de cuenta de recurso**. El tipo de cuenta de recurso puede ser **Operador automático** o **Cola de llamadas**, dependiendo de cómo desee usar esta cuenta de recursos.
4. Seleccione **Guardar**.

## <a name="assign-a-license"></a>Asignar una licencia

Para cada cuenta de recursos, debe asignar una licencia *estándar Teléfono Microsoft Teams - usuario virtual* o *una licencia de Teléfono Teams Estándar*.

1. En la Centro de administración de Microsoft 365, expanda **Usuarios** y, después, seleccione **Usuarios activos**.
2. Seleccione la cuenta de recursos a la que desea asignar una licencia. Aparecerá el panel de usuario de la cuenta de recursos.
3. En la pestaña **Licencias y aplicaciones**, en **Licencias**, seleccione **Teléfono Microsoft Teams Estándar - Usuario virtual**.
4. Seleccione **Guardar cambios**.

## <a name="assign-a-service-number"></a>Asignar un número de servicio

Si está pensando en usar la cuenta de recursos con un operador automático o una cola de llamadas que requiera un número de servicio, asigne un número a la cuenta de recursos.

1. En el centro de administración de Teams, en la página **Cuentas de** recursos, seleccione la cuenta de recursos a la que desea asignar un número de servicio y, a continuación, seleccione **Asignar o anular la asignación**.
2. En la **lista desplegable Teléfono tipo de número**, elija el tipo de número que desea usar.
3. En el cuadro **Número de teléfono asignado** , busque el número que desea usar y seleccione **Agregar**. Asegúrese de incluir el código de país (por ejemplo, +1 250 555 0012).
4. Seleccione **Guardar**.

Para asignar un número de enrutamiento directo o híbrido a una cuenta de recursos, debe usar PowerShell:

`Set-CsPhoneNumberAssignment -Identity aa-contoso_main@contoso64.net -PhoneNumber +19295550150 -PhoneNumberType DirectRouting`