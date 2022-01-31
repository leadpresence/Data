import java.io.Closeable
import kotlin.coroutines.EmptyCoroutineContext

class AggregateUserDataUseCase(
    private val resolveCurrentUser: suspend () -> UserEntity,
    private val fetchUserComments: suspend (UserId) -> List<CommentEntity>,
    private val fetchSuggestedFriends: suspend (UserId) -> List<FriendEntity>
) : Closeable {

    suspend fun aggregateDataForCurrentUser(): AggregatedData {
        TODO("implement task")
    }

    override fun close() {
        TODO("implement task")
    }
}

/**
 *
 * The following is already available on classpath.
 * Please do not uncomment this code or modify.
 * This is only for your convenience to copy-paste code into the IDE
package coroutines
data class AggregatedData(
val user: UserEntity,
val comments: List<CommentEntity>,
val suggestedFriends: List<FriendEntity>
)
typealias UserId = String
data class UserEntity(val id: UserId, val name: String)
data class CommentEntity(val id: String, val content: String)
data class FriendEntity(val id: String, val name: String)
 **/

data class AggregatedData(
    val user: UserEntity,
    val comments: List<CommentEntity>,
    val suggestedFriends: List<FriendEntity>
)

typealias UserId = String

data class UserEntity(val id: UserId, val name: String)

data class CommentEntity(val id: String, val content: String)

data class FriendEntity(val id: String, val name: String)

