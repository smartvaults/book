# Set profile and Contacts

In this section we show how to manage user profiles and contacts.

## Table of Contents

1. **Setting up Metadata and User Profiles**
2. **Retrieving the User Profile**
3. **Creating a New Contact**
4. **Adding or Updating a Contact**
5. **Fetching Contacts**
6. **Fetching Contacts with Metadata**

------

### Setting up Metadata and User Profiles

To set up a user profile, you need to use the `setProfile` method. Create a metadata object to include the details you wish to set in the profile.

```javascript
const metadata = { name: 'Bob', about: 'Learning about Smart Vaults!' };
await smartVaults.setProfile(metadata);
```

------

### Retrieving the User Profile

To fetch a profile, use the `getProfile` method.

```javascript
const myPublicKey = authenticator.getPublicKey();
const myProfile = await smartVaults.getProfile(myPublicKey);
```

------

### Creating a New Contact

To create a new contact, let's first generate a new set of Keys.

```javascript
const contactKeys = new Keys();
const contactAuthenticator = new DirectPrivateKeyAuthenticator(contactKeys.privateKey);
const contactPubKey = contactAuthenticator.getPublicKey();
```

------

### Creating and adding a contact

The `upsertContacts` method allows you add a new contact.

```javascript
const contact = new Contact({ publicKey: contactPubKey });
await smartVaults.upsertContacts(contact);
```

------

### Fetching Contacts

You can fetch your existing contacts using the `getContacts` method.

```javascript
const contacts = await smartVaults.getContacts();
```

------

### Fetching Contacts along with their metadata

To fetch contacts along with their profile metadata, you can use the `getContactProfiles` method.

```javascript
const contactsProfiles = await smartVaults.getContactProfiles();
```
