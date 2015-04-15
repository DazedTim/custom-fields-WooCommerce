# Adding custom fields into WooCommerce 'Bikes for sale' Category pages

Attempting to add custom fields in WooCommerce product pages and to display the fields in the front end.

I've registered the fields, I can save them, and they display in the product page.

I can't take out the information in a field and save it as blank.

The fields will display even if there is no info in them - I want them to display ONLY if they have info in.

*UPDATE*

Managed to fix it.

This was the old code:

$woocommerce_text_field = $_POST['_type_field'];
	if( !empty( $woocommerce_text_field ) )
	update_post_meta( $post_id, '_type_field', esc_attr( $woocommerce_text_field ) ); 
	
This is the new code:
	
$woocommerce_text_field = $_POST['_type_field'];
	if( isset( $woocommerce_text_field ) )
	update_post_meta( $post_id, '_type_field', esc_attr( $woocommerce_text_field ) ); 
	
I think the first snippet only saved when the field had something in it.
