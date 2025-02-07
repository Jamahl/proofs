# Home Depot Shopware POC - Content Deletion Process

This document outlines the process of identifying and deleting all existing content in the Home Depot Shopware instance. This step is crucial to ensure a clean slate for the new branding and product data.

## Content Deletion Steps

### 1. Retrieve Existing Categories

- **Action**: Retrieved all categories data including IDs and names.
- **Result**: Successfully identified the 'Catalogue #1' category which is essential to retain.
- **Data**:
  ```json
  {
    "categories": {
      "01938c22fc1b70f6b3dc798973f9eee1": "Catalogue #1",
      "77b959cf66de4c1590c7f9b7da3982f3": "Food",
      "19ca405790ff4f07aac8c599d4317868": "Bakery products",
      "48f97f432fd041388b2630184139cf0e": "Fish",
      "bb22b05bff9140f3808b1cff975b75eb": "Sweets",
      "a515ae260223466f8e37471d279e6406": "Clothing",
      "8de9b484c54f441c894774e5f57e485c": "Women",
      "2185182cbbd4462ea844abeb2a438b33": "Men",
      "251448b91bc742de85643f5fccd89051": "Free time & electronics"
    }
  }
  ```

### 2. Retrieve Media Folders

- **Action**: Retrieved IDs and names of 'Product Media' and 'Theme Media' folders.
- **Data**:
  ```json
  {
    "Product Media": {
      "id": "01938c22fce77355984343a2e42dc98a",
      "name": "Product Media"
    },
    "Theme Media": {
      "id": "01938c23038e72bd8e3c59bfa68fe68e",
      "name": "Theme Media"
    }
  }
  ```

### 3. Retrieve Product Media

- **Action**: Retrieved all media files in the 'Product Media' folder.
- **Data**:
  ```json
  {
    "media_files": {
      "102ac62ba27347a688030a05c1790db7": "shirt_600x600",
      "2de02991cd0548a4ac6cc35cb11773a0": "handschuh_600x600",
      "5808d194947f415495d9782d8fdc92ae": "hemd_600x600",
      "6968ad64888844679918c638e449ffc5": "schokolade_600x600",
      "6cbbdc03b43f4207be80b5f752d5a1c4": "shirt_blue_600x600",
      "70e352200b5c45098dc65a5b47094a2a": "mobile_600x600",
      "84356a71233d4b3e9f417dcc8850c82f": "waschmaschine_600x600",
      "f69ab8ae42d04e17b2bab5ec2ff0a93c": "shirt_red_600x600"
    }
  }
  ```

### 4. Retrieve Products and Related Entities

- **Action**: Retrieved all products, manufacturers, and property groups.
- **Data**:
  ```json
  {
    "products": {
      "01938c24813e73e3b27633e05605b8f7": null,
      "01938c24813e73e3b27633e056d94394": null,
      "01938c24813e73e3b27633e05776e74b": null,
      "01938c24813e73e3b27633e058599ea4": null,
      "01938c24813e73e3b27633e0593f1184": null,
      "01938c24813e73e3b27633e059ce0650": null,
      "01938c24813f7339855b5db674e28f39": null,
      "01938c24813f7339855b5db675799451": null,
      "01938c24813f7339855b5db675b1fee4": null,
      "01938c24813f7339855b5db675f7c36e": null,
      "11dc680240b04f469ccba354cbf0b967": "Main product with advanced prices",
      "1901dc5e888f4b1ea4168c2c5f005540": "Main product with reviews",
      "2a88d9b59d474c7e869d8071649be43c": "Main product",
      "3ac014f329884b57a2cce5a29f34779c": "Main product, free shipping with highlighting",
      "43a23e0c03bf4ceabc6055a2185faa87": "Variant product",
      "c7bca22753c84d08b6178a50052b4146": "Main product with properties"
    },
    "productManufacturers": {
      "01938c22fcae7286af7c8e320076445c": "shopware AG",
      "2326d67406134c88bcf80e52d9d2ecb7": "Shopware Food",
      "7f24e96676e944b0a0addc20d56728cb": "Shopware Fashion",
      "cc1c20c365d34cfb88bfab3c3e81d350": "Shopware Freetime"
    },
    "propertyGroups": {
      "1857bb30fe6448c88f8ad331cf6dfa0c": "Target group",
      "269c7e40a54a462e884edb004c5f7bc8": "Colour",
      "448f3d72803f4ac8afc0c1108739ddf4": "Ingredients",
      "75f353b589d04bf48e8a9ab1f5422b0e": "Size",
      "a67cdd9627cb488bb4cd91f3e8d66e32": "Material"
    }
  }
  ```

### 5. Delete Product Media Files

- **Action**: Deleted all media files in the 'Product Media' folder.
- **Result**: Successfully deleted all specified media files.
- **Deleted IDs**:
  ```json
  [
    "102ac62ba27347a688030a05c1790db7",
    "2de02991cd0548a4ac6cc35cb11773a0",
    "5808d194947f415495d9782d8fdc92ae",
    "6968ad64888844679918c638e449ffc5",
    "6cbbdc03b43f4207be80b5f752d5a1c4",
    "70e352200b5c45098dc65a5b47094a2a",
    "84356a71233d4b3e9f417dcc8850c82f",
    "f69ab8ae42d04e17b2bab5ec2ff0a93c"
  ]
  ```

### 6. Delete Categories Except 'Catalogue #1'

- **Action**: Deleted all categories except 'Catalogue #1'.
- **Result**: Successfully deleted specified categories.
- **Deleted IDs**:
  ```json
  [
    "77b959cf66de4c1590c7f9b7da3982f3",
    "a515ae260223466f8e37471d279e6406",
    "251448b91bc742de85643f5fccd89051"
  ]
  ```

### 7. Delete Products and Related Entities

- **Action**: Deleted all products, manufacturers, and property groups.
- **Result**: Successfully deleted all specified entities.
- **Deleted Products IDs**:
  ```json
  [
    "01938c24813e73e3b27633e05605b8f7",
    "01938c24813e73e3b27633e056d94394",
    "01938c24813e73e3b27633e05776e74b",
    "01938c24813e73e3b27633e058599ea4",
    "01938c24813e73e3b27633e0593f1184",
    "01938c24813e73e3b27633e059ce0650",
    "01938c24813f7339855b5db674e28f39",
    "01938c24813f7339855b5db675799451",
    "01938c24813f7339855b5db675b1fee4",
    "01938c24813f7339855b5db675f7c36e",
    "11dc680240b04f469ccba354cbf0b967",
    "1901dc5e888f4b1ea4168c2c5f005540",
    "2a88d9b59d474c7e869d8071649be43c",
    "3ac014f329884b57a2cce5a29f34779c",
    "43a23e0c03bf4ceabc6055a2185faa87",
    "c7bca22753c84d08b6178a50052b4146"
  ]
  ```
- **Deleted Manufacturers IDs**:
  ```json
  [
    "01938c22fcae7286af7c8e320076445c",
    "2326d67406134c88bcf80e52d9d2ecb7",
    "7f24e96676e944b0a0addc20d56728cb",
    "cc1c20c365d34cfb88bfab3c3e81d350"
  ]
  ```
- **Deleted Property Groups IDs**:
  ```json
  [
    "1857bb30fe6448c88f8ad331cf6dfa0c",
    "269c7e40a54a462e884edb004c5f7bc8",
    "448f3d72803f4ac8afc0c1108739ddf4",
    "75f353b589d04bf48e8a9ab1f5422b0e",
    "a67cdd9627cb488bb4cd91f3e8d66e32"
  ]
  ```

## Conclusion

The content deletion process was successfully executed, ensuring a clean environment for the new Home Depot branding and product data. All specified entities were removed without errors, as confirmed by the Shopware API responses.
