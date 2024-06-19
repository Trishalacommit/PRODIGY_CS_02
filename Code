from PIL import Image
import numpy as np
import sys

def encrypt_image(input_path, output_path, key):
    # Open the image
    image = Image.open(input_path)
    image_array = np.array(image)
    
    # Encrypt the image by modifying pixel values
    encrypted_array = (image_array + key) % 256
    
    # Convert back to image and save
    encrypted_image = Image.fromarray(encrypted_array.astype('uint8'))
    encrypted_image.save(output_path)

def decrypt_image(input_path, output_path, key):
    # Open the image
    image = Image.open(input_path)
    image_array = np.array(image)
    
    # Decrypt the image by reversing the modification
    decrypted_array = (image_array - key) % 256
    
    # Convert back to image and save
    decrypted_image = Image.fromarray(decrypted_array.astype('uint8'))
    decrypted_image.save(output_path)

def main():
    if len(sys.argv) < 5:
        print("Usage: python image_encryptor.py <encrypt/decrypt> <input_path> <output_path> <key>")
        return
    
    action = sys.argv[1]
    input_path = sys.argv[2]
    output_path = sys.argv[3]
    key = int(sys.argv[4])
    
    if action == 'encrypt':
        encrypt_image(input_path, output_path, key)
        print(f"Image encrypted and saved to {output_path}")
    elif action == 'decrypt':
        decrypt_image(input_path, output_path, key)
        print(f"Image decrypted and saved to {output_path}")
    else:
        print("Invalid action. Use 'encrypt' or 'decrypt'.")

if __name__ == "__main__":
    main()
