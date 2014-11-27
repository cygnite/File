File Component
===========

Cygnite file component handling file upload and creating thumbnail image etc.

Upload file using file component.
  
Example Usage:

	use Cygnite\Common\File\Upload\Upload;

	$status = Upload::process( function($upload)
	{
		// Your code goes here
		$upload->file = 'document';
		$upload->ext = array("JPG");
		$upload->size = '32092';

		if ( $upload->save(array("destination"=> "upload", "fileName"=>"file_new_name")) ) {
			 // Upload Success
		} else {
			 // Error catch here
		}
	});
	
	// var_dump($status);
	
	
Image Cropping / Thumbnail Image:
	
Make thumbnail image.
	
Example Usage:


	use Cygnite\Common\File\Thumbnail\Image;

	$thumb = new Image();
	$thumb->directory = 'Set your directory path';
	$thumb->fixedWidth = 100;
	$thumb->fixedHeight = 100;
	$thumb->thumbPath = 'your thumbnail image path';
	$thumb->thumbName = 'Your thumbnail image name';
	// Optional. If you doen't want to have custom name then it will generate thumb as same name of original image.
	$thumb->resize();
