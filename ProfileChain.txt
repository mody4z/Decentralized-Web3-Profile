// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

/**
 * @title ProfileChain
 * @dev A decentralized identity registry on Celo blockchain
 * @notice This contract allows users to create and manage their professional profiles on-chain
 */
contract ProfileChain {
    
    // Structure to store user profile information
    struct UserProfile {
        string name;
        string bio;
        string portfolioUrl;
        bool exists;
    }
    
    // Mapping from user address to their profile
    mapping(address => UserProfile) private profiles;
    
    // Event emitted when a profile is created or updated
    event ProfileUpdated(
        address indexed user,
        string name,
        string bio,
        string portfolioUrl
    );
    
    /**
     * @dev Creates or updates a user's profile
     * @param _name The user's full name
     * @param _bio A short biography or description
     * @param _portfolioUrl URL to the user's portfolio or website
     */
    function setProfile(
        string memory _name,
        string memory _bio,
        string memory _portfolioUrl
    ) public {
        require(bytes(_name).length > 0, "Name cannot be empty");
        require(bytes(_bio).length > 0, "Bio cannot be empty");
        require(bytes(_portfolioUrl).length > 0, "Portfolio URL cannot be empty");
        
        profiles[msg.sender] = UserProfile({
            name: _name,
            bio: _bio,
            portfolioUrl: _portfolioUrl,
            exists: true
        });
        
        emit ProfileUpdated(msg.sender, _name, _bio, _portfolioUrl);
    }
    
    /**
     * @dev Retrieves a user's profile by their address
     * @param user The address of the user whose profile to retrieve
     * @return name The user's name
     * @return bio The user's bio
     * @return portfolioUrl The user's portfolio URL
     * @return exists Whether the profile exists
     */
    function getProfile(address user) 
        public 
        view 
        returns (
            string memory name,
            string memory bio,
            string memory portfolioUrl,
            bool exists
        ) 
    {
        UserProfile memory profile = profiles[user];
        return (
            profile.name,
            profile.bio,
            profile.portfolioUrl,
            profile.exists
        );
    }
    
    /**
     * @dev Retrieves the caller's own profile
     * @return name The caller's name
     * @return bio The caller's bio
     * @return portfolioUrl The caller's portfolio URL
     * @return exists Whether the profile exists
     */
    function getMyProfile() 
        public 
        view 
        returns (
            string memory name,
            string memory bio,
            string memory portfolioUrl,
            bool exists
        ) 
    {
        return getProfile(msg.sender);
    }
    
    /**
     * @dev Checks if a user has a profile
     * @param user The address to check
     * @return bool True if the user has a profile, false otherwise
     */
    function hasProfile(address user) public view returns (bool) {
        return profiles[user].exists;
    }
}
